# Planificación y gestión de recursos: CUIDALIA

## 1. Introducción y objetivos

Este documento recoge la planificación de recursos materiales, herramientas, infraestructura cloud, APIs y equipo humano de CUIDALIA para los 6 sprints de desarrollo del proyecto. Da respuesta a los **Criterios 3b (Asignación de recursos y logística)** y **3f (Planificación de recursos materiales, humanos y tiempos)** de la guía oficial del proyecto intermodular de DAW del IES Rafael Alberti.

Aquí se detalla:
1. Los **servicios cloud** elegidos (hosting del frontend, hosting del backend, base de datos NoSQL y dominios).
2. Las **APIs externas**, sus límites de uso y la alternativa de respaldo en caso de fallo.
3. El control de **contraseñas y variables de entorno** con Bitwarden y archivos `.env`.
4. Las **herramientas de desarrollo, diseño y pruebas** utilizadas por el equipo.
5. Los perfiles de los integrantes y la **tabla de rotación de roles SCRUM** (Product Owner, Scrum Master y Desarrollador) a lo largo de los 6 sprints, alineada con la Wiki del repositorio.
6. La forma de estimar tareas mediante **Planning Poker**, el cálculo de la velocidad del equipo y el margen para imprevistos.
7. El presupuesto económico real en fase académica y la estimación de costes si el proyecto se lanzara a producción.

---

## 2. Recursos materiales e infraestructura cloud

Durante el desarrollo académico del MVP usamos planes gratuitos (*Free Tier*) de servicios en la nube para mantener el coste en 0 € sin perder funciones esenciales como despliegues automáticos (CI/CD) o conexiones seguras HTTPS.

### 2.1. Frontend: Vercel

- **Servicio:** Alojamiento estático y red de distribución (CDN) de Vercel.
- **Plan:** Hobby (Gratuito).
- **Uso:** Servir la aplicación cliente desarrollada en React con Vite y Tailwind CSS.
- **Límites técnicos:**
  - 100 GB de transferencia mensual.
  - 1 proceso de compilación simultáneo.
  - Subdominio seguro automático: `cuidalia.vercel.app` con certificado SSL de Let's Encrypt.
- **Despliegue continuo (CI/CD):**
  - Cada vez que se hace merge a la rama principal en GitHub, Vercel compila y publica los cambios de forma automática.
  - Genera enlaces de prueba temporales (*Preview Deployments*) en cada Pull Request para revisar la interfaz antes de fusionar el código.
- **Ajustes:** Compilación minificada con Vite y división en fragmentos (*code splitting*) para que la web cargue rápido en conexiones móviles lentas.

### 2.2. Backend: Render

- **Servicio:** Web Service en contenedor Linux gestionado por Render.
- **Plan:** Free Web Service.
- **Uso:** Ejecutar la API REST programada con Node.js y Express.
- **Límites técnicos:**
  - 512 MB de memoria RAM y 0.1 CPU compartida.
  - 750 horas de ejecución al mes por cuenta.
  - Almacenamiento efímero (sin disco duro permanente; todos los datos se guardan en la base de datos).
  - Dirección segura: `cuidalia-api.onrender.com` con cifrado HTTPS automático.
- **Gestión del reposo (*Spin-down*):**
  - En la capa gratuita, el servidor se duerme tras 15 minutos sin peticiones. La primera llamada puede tardar unos 50 segundos en responder mientras se reactiva el contenedor.
  - *Solución:* Hemos creado una ruta `/api/health` para hacer comprobaciones periódicas durante las horas de pruebas y demostraciones de evaluación.

### 2.3. Base de datos: MongoDB Atlas

- **Servicio:** Base de datos documental NoSQL gestionada en la nube por MongoDB.
- **Plan:** Clúster M0 Sandbox (Gratuito).
- **Uso:** Guardar las colecciones del sistema (`users`, `assistedPersons`, `visits`, `substitutionRequests`, `notifications`).
- **Límites y características:**
  - 512 MB de almacenamiento (suficiente para decenas de miles de registros en texto y JSON).
  - Réplica de alta disponibilidad formada por 3 nodos (un servidor primario y dos de respaldo que toman el relevo si el principal falla).
  - Región en Europa (Frankfurt o Irlanda) para cumplir con el RGPD y no alojar datos fuera de la Unión Europea.
- **Seguridad:**
  - Conexiones cifradas con TLS 1.3.
  - Lista blanca de IPs para que solo los servidores de Render y los ordenadores del equipo puedan conectar con la base de datos.
  - Usuario de base de datos con contraseña robusta y permisos limitados a la base de datos `cuidalia_db`.

### 2.4. Dominios y certificados

- **En desarrollo:** Usamos los subdominios HTTPS que ofrecen Vercel y Render (`cuidalia.vercel.app` y `cuidalia-api.onrender.com`), que incluyen certificados SSL gratuitos y no suponen ningún coste.
- **En producción real:** Contrataríamos un dominio propio (`cuidalia.es` o `cuidalia.com`) a través de un registrador como DonDominio o Cloudflare por unos 10 € - 15 € al año.

---

## 3. APIs externas y planes de respaldo

### 3.1. OpenRouteService (ORS API)

- **Qué hace:** Es un servicio abierto basado en OpenStreetMap que calcula rutas y tiempos de trayecto.
- **Función en CUIDALIA:** Calcula cuánto tarda una cuidadora en llegar desde su ubicación o servicio anterior hasta el domicilio de una baja, ya sea en coche, en bicicleta o andando, y ordena a las candidatas por tiempo de llegada.
- **Límites del plan gratuito:**
  - 500 peticiones al día.
  - Máximo de 40 peticiones por minuto.
- **Seguridad:** La clave de la API se guarda en el archivo `.env` del servidor (`OPENROUTESERVICE_API_KEY`). El frontend nunca tiene acceso a la clave para evitar que nadie la extraiga del código.
- **Plan de respaldo (Fórmula de Haversine):**
  - Si se agotan las 500 peticiones diarias o el servicio de OpenRouteService se cae, el backend no se bloquea.
  - En su lugar, activa una función matemática interna que calcula la distancia en línea recta sobre la esfera terrestre usando la fórmula de Haversine:
    $$\Delta\sigma = 2 \arcsin \left( \sqrt{\sin^2\left(\frac{\Delta\phi}{2}\right) + \cos(\phi_1)\cos(\phi_2)\sin^2\left(\frac{\Delta\lambda}{2}\right)} \right)$$
    $$d = R \cdot \Delta\sigma$$
    *(con radio terrestre $R = 6.371\text{ km}$, latitud $\phi$ y longitud $\lambda$).*
  - Con esa distancia, el servidor calcula un tiempo estimado según el transporte de la cuidadora (4 km/h a pie, 15 km/h en bici o 30 km/h en coche) y la sustitución puede seguir adelante sin depender de la API externa.

### 3.2. Web-Push y claves VAPID

- **Qué hace:** Envía avisos al móvil o al navegador a través del Service Worker de la PWA.
- **Función en CUIDALIA:** Avisar a las cuidadoras cuando hay una baja disponible para aceptar y notificar a las familias si ocurre una emergencia o cuando el auxiliar marca la entrada.
- **Coste y límites:** Es un estándar abierto del W3C, por lo que es gratuito y no tiene límite de avisos.
- **Cómo se usa:** Con la librería `web-push` en Node.js y dos claves criptográficas (VAPID):
  - `VAPID_PUBLIC_KEY`: Se envía al navegador para registrar la suscripción.
  - `VAPID_PRIVATE_KEY`: Se queda en el servidor para firmar los mensajes.

---

## 4. Contraseñas, accesos y variables de entorno

Al tratar información de salud y domicilios particulares, cuidamos la seguridad de los accesos:

### 4.1. Gestor de contraseñas (Bitwarden)

Para no pasarnos claves por WhatsApp ni dejarlas escritas en notas, usamos **Bitwarden**:
- Creamos una organización compartida donde los cuatro miembros del equipo (Dani, Irene, Alejandro y Pablo) tienen acceso a los accesos comunes.
- Obligatorio activar **verificación en dos pasos (2FA)** en cada cuenta personal.
- Claves guardadas en la bóveda: usuario de MongoDB Atlas, cuentas de Vercel y Render, clave de OpenRouteService y claves VAPID.

### 4.2. Variables de entorno

- **En local:** Los datos sensibles van en el archivo `.env` de cada ordenador y no se suben nunca a Git.
- **En el repositorio:** El archivo `.gitignore` incluye `.env` para evitar subidas por error. Dejamos un archivo de plantilla `.env.example` con los nombres de las variables sin las contraseñas reales.
- **En producción:** Las variables se configuran en el panel de control privado de Render, Vercel y en los secretos de GitHub Actions.

#### Variables de entorno del proyecto

| Variable | Dónde se usa | Para qué sirve |
|---|---|---|
| `PORT` | Backend | Puerto del servidor (por defecto `5000` en local). |
| `NODE_ENV` | Backend | Entorno (`development` en local o `production` en Render). |
| `CLIENT_URL` | Backend | Dirección permitida por CORS (ej. `http://localhost:5173` o `https://cuidalia.vercel.app`). |
| `MONGODB_URI` | Backend | Dirección de conexión con usuario y contraseña a MongoDB Atlas. |
| `JWT_SECRET` | Backend | Clave para firmar el token de sesión corto (dura 15 minutos). |
| `JWT_REFRESH_SECRET` | Backend | Clave para el token de refresco en cookie `httpOnly` (dura 7 días). |
| `OPENROUTESERVICE_API_KEY` | Backend | Clave para consultar rutas en OpenRouteService. |
| `VAPID_PUBLIC_KEY` | Backend y Front | Clave pública para las notificaciones push. |
| `VAPID_PRIVATE_KEY` | Backend | Clave secreta para autorizar el envío de notificaciones. |
| `VAPID_SUBJECT` | Backend | Correo de contacto que exige el estándar VAPID. |

---

## 5. Herramientas de trabajo del equipo

| Herramienta | Tipo | Uso en CUIDALIA |
|---|---|---|
| **Visual Studio Code** | Editor de código | Editor común para todo el equipo, con extensiones de ESLint, Prettier y Tailwind CSS. |
| **Git y GitHub** | Control de versiones | Repositorio central (`ifonlob/Cuidalia`). Trabajamos con ramas por funcionalidad y revisiones de código en cada PR. |
| **GitHub Projects** | Gestión ágil | Tablero Kanban con los campos: Sprint, Prioridad, Estimación (horas), Categoría, Estado y Assignee. |
| **Toggl Track** | Control de tiempo | Cada integrante cronometra el tiempo real dedicado a cada tarea para compararlo con lo estimado. |
| **Figma** | Diseño | Bocetos de pantallas y prototipos antes de programar las vistas en React. |
| **Postman / Thunder Client** | Pruebas de API | Colecciones de peticiones para probar los endpoints del servidor antes de conectarlos con el frontend. |
| **Vitest** | Pruebas de código | Tests unitarios para funciones críticas (como la fórmula de Haversine o validaciones de fecha). |
| **Maestro** | Pruebas visuales | Tests automáticos para comprobar los recorridos de pantalla principales de la PWA. |

---

## 6. Equipo humano y rotación de roles SCRUM

El equipo está formado por cuatro personas: **Dani, Irene, Alejandro y Pablo**. Siguiendo la metodología SCRUM y la guía del profesor, nos repartimos las responsabilidades técnicas y rotamos en cada sprint por los roles de **Product Owner**, **Scrum Master** y **Desarrollador**.

### 6.1. Integrantes y áreas de trabajo

- **Dani:** Mayor soltura inicial en maquetación de pantallas; refuerza el desarrollo de endpoints en Express, modelos de base de datos y validaciones con Zod.
- **Irene:** Coordinación del producto, diseño de pantallas en Figma, maquetación con React y Tailwind CSS, y documentación normativa y legal (RGPD).
- **Alejandro:** Arquitectura del backend, conexión con MongoDB/Mongoose, rutas de la API, integración con OpenRouteService, gestión de recursos y análisis de mercado.
- **Pablo:** Desarrollo frontend en React, control de formularios, presupuestos del proyecto, cálculo de costes y soporte en documentación técnica.

### 6.2. Tabla de rotación de roles por sprint

Esta rotación coincide exactamente con la registrada en la Wiki del repositorio (`Roles-del-equipo.md`), asegurando que todos asumimos los distintos roles a lo largo de las 12 semanas (6 sprints de 2 semanas):

| Sprint | Objetivo del Sprint | Product Owner (PO) | Scrum Master (SM) | Resto del equipo (Devs) |
|:---:|---|:---:|:---:|---|
| **Sprint 1** | Configuración base del repositorio, arquitectura MERN y conexión a MongoDB. | **Dani** | **Irene** | Alejandro y Pablo |
| **Sprint 2** | Autenticación de usuarios, roles (coordinador, cuidador, familiar) y protección JWT. | **Irene** | **Alejandro** | Dani y Pablo |
| **Sprint 3** | Vistas de cuadrantes para coordinación y filtro de servicios afectados por bajas. | **Alejandro** | **Pablo** | Dani e Irene |
| **Sprint 4** | Recorrido completo de sustitución: candidatos, cálculo de rutas y aceptación. | **Pablo** | **Dani** | Irene y Alejandro |
| **Sprint 5** | Pruebas unitarias, accesibilidad, PWA, notificaciones push y revisión legal. | **Dani** | **Alejandro** | Irene y Pablo |
| **Sprint 6** | Despliegue en producción (Vercel + Render), pruebas E2E con Maestro y entrega. | **Irene** | **Pablo** | Dani y Alejandro |

### 6.3. Tareas de cada rol

- **Product Owner (PO):** Ordena el Backlog en GitHub Projects, explica qué debe hacer cada tarea, aclara dudas funcionales y comprueba que lo entregado cumple con el objetivo del sprint.
- **Scrum Master (SM):** Dirige las reuniones cortas (Daily y Planning), ayuda si alguien tiene un bloqueo técnico, comprueba que GitHub Projects y Toggl Track estén al día y vigila que las horas de trabajo queden repartidas entre todos.
- **Equipo de desarrollo (Devs):** Estima el esfuerzo de las tareas en el Planning Poker, programa el código, escribe pruebas y revisa las Pull Requests de sus compañeros antes de integrarlas.

---

## 7. Estimación de tareas y balanceo de carga

Para cumplir con el **Criterio 3b**, organizamos la estimación de la siguiente manera:

### 7.1. Dinámica de Planning Poker

1. En la reunión de inicio del sprint (Sprint Planning), el Product Owner lee una tarea y sus condiciones.
2. Cada miembro elige en secreto un número de la serie de Fibonacci:
   $$\{1, 2, 3, 5, 8, 13\}$$
   Cada número representa horas de trabajo previstas.
3. Mostramos la puntuación a la vez:
   - Si casi todos coincidimos, dejamos ese valor.
   - Si hay mucha diferencia (por ejemplo, alguien dice 2 horas y otro 8), los que votaron los extremos explican su motivo (si conocen alguna dificultad o si ya tienen código previo que lo simplifica). Tras hablar 2 minutos, volvemos a votar y consensuamos el número final.
4. **Límite de 8 horas:** Si una tarea se valora en 13 o más horas, la dividimos en dos tareas más pequeñas antes de empezar.
5. El número acordado se guarda en el campo **Estimación (horas)** de la tarjeta en GitHub Projects.

### 7.2. Margen para imprevistos (Buffer)

Como trabajar con librerías nuevas o configurar servicios en la nube puede dar fallos imprevistos, dejamos un **15% de tiempo de margen** en cada sprint. Además, para temas difíciles que nadie domina (como la configuración inicial de la PWA), creamos una tarea previa de investigación limitada a un máximo de 4 o 5 horas.

### 7.3. Reparto de horas y velocidad del equipo

- Cada miembro asume unas 10 horas de trabajo por semana (40 horas de equipo semanales / 80 horas por sprint), coincidiendo con las previsiones de `docs/presupuesto.md`. El Scrum Master vigila que nadie se quede con más de 25 horas ni con menos de 15 en un mismo sprint.
- Al terminar el sprint, sumamos las horas estimadas de las tareas que están en **Done**. Esa suma es la velocidad del equipo y nos sirve para saber cuánto trabajo podemos meter en el siguiente sprint sin sobrecargarnos.

---

## 8. Presupuesto económico de recursos

Siguiendo los criterios 2f y 3f, distinguimos entre los costes reales del desarrollo en clase y lo que costaría mantener la aplicación funcionando para clientes reales.

### 8.1. Coste real durante el desarrollo (Fase académica)

| Recurso | Proveedor | Plan | Coste mensual | Total en 6 Sprints |
|---|---|---|:---:|:---:|
| Hosting Frontend | Vercel | Hobby (Free Tier) | 0,00 € | 0,00 € |
| Hosting Backend | Render | Free Web Service | 0,00 € | 0,00 € |
| Base de datos NoSQL | MongoDB Atlas | M0 Sandbox | 0,00 € | 0,00 € |
| Dominio y SSL | Vercel / Render | Subdominio HTTPS incluido | 0,00 € | 0,00 € |
| API de rutas | OpenRouteService | Standard Free (500 req/día) | 0,00 € | 0,00 € |
| Notificaciones | Web-Push / VAPID | Estándar W3C abierto | 0,00 € | 0,00 € |
| Gestor de claves | Bitwarden | Plan gratuito con 2FA | 0,00 € | 0,00 € |
| Repositorio y CI/CD | GitHub | Plan gratuito | 0,00 € | 0,00 € |
| **Total materiales** | — | — | **0,00 €** | **0,00 €** |

### 8.2. Estimación si se lanzara como empresa real (50 pymes clientes)

Si CUIDALIA se pusiera en marcha para 50 empresas de ayuda a domicilio (unos 500 auxiliares y 2.000 usuarios atendidos), los servicios tendrían que pasar a planes de pago con garantías de disponibilidad:

| Recurso | Proveedor / Plan | Motivo | Coste mensual | Coste anual |
|---|---|---|:---:|:---:|
| **Dominio propio** | DonDominio / Cloudflare | Dirección corporativa `.es` y `.com` con protección web | ~ 1,25 € | 15,00 € |
| **Frontend Pro** | Vercel Pro | Ancho de banda comercial y soporte de tráfico concurrente | ~ 18,50 € ($20) | 222,00 € |
| **Backend permanente** | Render Team / Starter | Servidor siempre activo (sin spin-down), con 1 GB RAM y backups | ~ 23,00 € ($25) | 276,00 € |
| **Base de datos dedicada** | MongoDB Atlas M10 | Clúster propio con 10 GB de disco y copias de seguridad continuas | ~ 55,00 € ($60) | 660,00 € |
| **API de rutas sin límite** | Servidor Hetzner / Docker ORS | Motor OpenRouteService autoalojado en un servidor propio | 35,00 € | 420,00 € |
| **Bóveda de claves** | Bitwarden Teams | Gestión de accesos con permisos por departamentos | ~ 11,00 € ($12) | 132,00 € |
| **Correos del sistema** | Resend / SendGrid | Envío de notificaciones por email a familias y altas de usuario | 15,00 € | 180,00 € |
| **Total anual estimado** | — | — | **~ 158,75 € / mes** | **~ 1.905,00 € / año** |

Esto demuestra que el proyecto es viable técnicamente y económicamente: se puede construir y probar en clase a coste cero, y en caso de comercializarse tendría un coste de servidores de menos de 40 € al año por cada empresa cliente.
