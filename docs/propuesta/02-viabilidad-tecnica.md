# Viabilidad técnica

## Introducción

En este apartado se analiza la viabilidad técnica del proyecto, evaluando las tecnologías necesarias para desarrollar el MVP, las capacidades del equipo, la infraestructura disponible y los principales riesgos técnicos. El objetivo es determinar si es posible implementar las funcionalidades prioritarias dentro del plazo previsto y con los recursos disponibles.
---

## 1. Requisitos funcionales

## 1. Persona principal: Coordinador/a

### Gestionar el cuadrante de horarios
El coordinador crea y modifica los horarios de usuarios y trabajadores desde una vista que muestra disponibilidades, vacaciones y huecos libres. Así deja de rehacer cuadrantes enormes en Excel cada vez que hay un cambio.

### Asignar un trabajador a un usuario
El coordinador busca al cuidador adecuado con filtros de compatibilidad:

- Fuerza para usar grúa.
- Experiencia en demencias.
- Alergias a mascotas.
- Baño adaptado.
- Carácter.
- Distancia al domicilio.

Esto reduce los emparejamientos fallidos, que obligan a empezar de cero.

### Gestionar el perfil del usuario
El coordinador registra y actualiza la siguiente información:

- Grado de dependencia.
- Necesidad de aseo en cama.
- Medicación.
- Horario contratado.
- Contactos de la familia.

Toda esa información queda en un único lugar, en vez de repartida entre papel, Excel y WhatsApp.

### Gestionar bajas y sustituciones
Cuando un trabajador no puede acudir, el coordinador envía un aviso a varios cuidadores disponibles a la vez y el primero que acepta desde la app se queda con el servicio.

Se evita llamar uno por uno a quienes libraban.

### Notificar cambios a familia y cuidadores
El sistema avisa automáticamente de los cambios de horario o de trabajador. El coordinador deja de hacer de «centralita».

### Monitorizar las visitas en tiempo real
El coordinador ve quién ha llegado, quién se retrasa y quién no se ha presentado, y recibe alertas.

Así detecta los fallos antes de que la familia llame para quejarse.

### Gestionar incidencias
El coordinador registra, prioriza y hace seguimiento de las incidencias, como:

- Bajas.
- Síntomas extraños.
- Cambios por citas médicas.
- Malas noches.

Todas quedan documentadas y no solo comunicadas por teléfono.

### Consultar ubicación y huecos de los trabajadores
El coordinador ve dónde está cada trabajador y qué huecos reales tiene, sin revisar el Excel celda por celda.

### Generar el informe de horas para nóminas
El sistema calcula las horas trabajadas y las sustituciones del mes.

Desaparecen los post-its y los colores en Excel.

### Revisar el historial de tareas
El coordinador consulta lo realizado en cada visita, con seguimiento diario y no solo la hoja de firmas mensual.

### Comunicarse por mensajería interna
El coordinador se comunica con familias y cuidadores desde un canal único, sin líneas saturadas ni WhatsApps dispersos.

---

## 2. Persona secundaria 1: Familiar

### Consultar el resumen diario de tareas
El familiar abre la app y ve de un vistazo:

- Medicación.
- Comida.
- Aseo.
- Cómo ha dormido su familiar.
- Su estado de ánimo.

Así no tiene que llamar a la oficina ni esperar a la tarde para saberlo.

### Recibir alertas inmediatas
Ante un mareo, una caída u otro evento grave, el familiar recibe una notificación destacada en el móvil.

### Solicitar cambios o necesidades
El familiar pide, por ejemplo, adelantar la visita por una cita médica o aplicar una crema en la pierna derecha, y ve el estado de la solicitud.

Evita las esperas de dos horas y la pérdida de detalles por el «teléfono escacharrado».

### Conocer al cuidador sustituto
El familiar recibe un aviso anticipado del cambio y puede ver el nombre, la foto, la experiencia y la formación de la persona nueva.

Así no se entera por su padre de que ha venido alguien desconocido.

### Chatear con coordinación o con el cuidador
El familiar tiene un canal directo y transparente, sin sentir que molesta.

### Consultar el calendario de visitas
El familiar sabe quién va a ir y cuándo.

### Usar la app cómodamente desde el móvil
La interfaz es visual, con pocos menús y sesión persistente, porque el familiar dispone de poco tiempo.

---

## 3. Persona secundaria 2: Cuidador/a

### Consultar la agenda personal
El cuidador ve sus servicios, direcciones y horarios, y recibe los cambios en tiempo real.

Sustituye al cuadrante en papel o a la foto de WhatsApp.

### Avisar de que no puede acudir
El cuidador pulsa un botón de baja y el sistema avisa a coordinación automáticamente.

Se acaban las llamadas a una oficina saturada.

### Ver el perfil del usuario
El cuidador consulta la siguiente información antes de la visita, sobre todo en las primeras:

- Movilidad.
- Patologías.
- Alergias.
- Mascotas.
- Medicación.
- Dieta.

### Consultar notas y rutinas del usuario
El cuidador ve las manías del usuario, la rutina del cuidador titular y dónde están los objetos clave.

Es especialmente útil en las sustituciones.

### Registrar llegada y salida
El cuidador hace *check-in* y *check-out*, con geolocalización.

Esto le protege ante reclamaciones y justifica el tiempo real en el domicilio.

### Marcar las tareas realizadas
El cuidador completa un *checklist* detallado con medicación a su hora, comida, aseo y cremas, en lugar de la hoja de papel y de tareas genéricas.

### Reportar incidencias
El cuidador registra situaciones como:

- Negativas a medicarse.
- Caídas.
- Falta de material.
- Peticiones fuera del plan.

Así no depende de una llamada.

### Activar un botón de emergencia
El cuidador avisa a coordinación y a la familia a la vez, y tiene a mano los contactos que necesita en una urgencia.

### Recibir avisos de cambios importantes
El cuidador es informado de cambios en medicación, movilidad o citas, con confirmación de lectura.

---

## 4. Priorización de funcionalidades

### 4.1. Must have

Funcionalidades imprescindibles para la primera versión del producto:

- **Autenticación y roles:** sin permisos diferenciados, la familia vería datos que no debe.
- **Cuadrante:** crear y editar servicios manualmente.
- **Perfil del usuario:** dependencia, medicación, horario contratado y contactos de la familia.
- **Bajas y sustituciones:** aviso a los candidatos y aceptación desde la app.
- **Notificaciones de cambios:** a familia y cuidadores.
- **Monitorización de visitas:** quién ha llegado, quién se retrasa y quién no ha aparecido.
- **Perfil del cuidador.**
- **Perfil del usuario visible para el cuidador.**
- **Check-in y check-out.**
- **Checklist de tareas realizadas.**

### 4.2. Should have

Funcionalidades importantes que pueden incorporarse después de las imprescindibles:

- **Incidencias:** el coordinador las gestiona y el cuidador las reporta.
- **Historial de tareas consultable.**
- **Alertas inmediatas de eventos graves.**
- **Solicitudes de la familia:** por ejemplo, adelantar una visita.

---

## 5. Producto Mínimo Viable (MVP)

### 5.1. Coordinador/a: recorrido mínimo para gestionar una baja

**Objetivo:** permitir que el coordinador encuentre una sustitución para un servicio afectado por la baja de un trabajador.

1. En la pestaña principal, toca el apartado **«Cuadrantes»**.
2. Una vez dentro, filtra por el trabajador que se ha dado de baja.
3. Selecciona el turno afectado.
4. Pulsa el botón **«Asignar sustitución»**.
5. En el *pop-up* de **«Detalles del turno»**, elige a un trabajador disponible.
6. Pulsa el botón **«Asignar turno»**.
7. El trabajador acepta el turno en su app.

### 5.2. Familiar: recorrido mínimo para asegurarse de que todo ha ido bien

**Objetivo:** permitir que el familiar compruebe que el servicio ha finalizado y que las tareas se han realizado correctamente.

1. El familiar entra en la aplicación mediante una notificación que avisa sobre el fin del trabajo.
2. Comprueba que la sesión no ha caducado.
3. Entra en el **«Resumen del día»**.
4. Revisa que las tareas hayan ido bien.
5. Cierra la aplicación y mantiene la calma.

### 5.3. Cuidador/a: recorrido mínimo para completar un servicio sin incidencias

**Objetivo:** permitir que el cuidador registre su llegada, complete las tareas asignadas y guarde el resultado del servicio.

1. El trabajador llega a la puerta de la casa del usuario, abre la app y la aplicación verifica si hay cobertura en el interior.
2. El trabajador accede a la pantalla **«Mis turnos hoy»** y selecciona el turno actual.
3. Dentro de la **«Ficha del servicio actual»**, pulsa el botón **«Fichar entrada»**. El sistema registra la hora de entrada y el trabajador pulsa **«Ver tareas»**.
4. Se muestra el **«Checklist de tareas específicas»**. Al no surgir ninguna anomalía durante el servicio, el trabajador simplemente va marcando los checks de las tareas completadas.
5. Como no ha dejado tareas obligatorias sin marcar, el sistema valida la información automáticamente. Se genera el mensaje **«Resumen del servicio guardado con éxito y sincronizado»**, tras lo cual el trabajador cierra la aplicación y se desplaza a la siguiente casa.

---

## 6. Resumen de los perfiles y sus objetivos

| Perfil | Objetivo principal |
|---|---|
| **Coordinador/a** | Gestionar horarios, asignaciones, sustituciones e incidencias desde un único lugar. |
| **Familiar** | Consultar el estado de su familiar, conocer las visitas y comunicarse con coordinación. |
| **Cuidador/a** | Consultar sus servicios, registrar la jornada, completar tareas y comunicar incidencias. |

## 7. Resumen del alcance del MVP

El MVP se centra en tres recorridos esenciales:

1. **Coordinación:** gestionar una baja y asignar una sustitución.
2. **Familiar:** consultar el resumen diario tras finalizar el servicio.
3. **Cuidador/a:** fichar la entrada, completar las tareas y guardar el servicio.

Estos recorridos permiten validar el funcionamiento básico de la gestión de servicios, la comunicación entre perfiles y el seguimiento de las visitas.


---

## 2. Análisis de requisitos técnicos

### 2.1 Frontend (React)

- **React DOM**: interactuar con el DOM de la aplicación.
- **React Router**: navegar entre las distintas páginas de la aplicación y proteger las rutas según el rol del usuario.
- **Tailwind CSS**: estilos de la aplicación, con diseño adaptable a móvil.
- **Vite**: crear y compilar el proyecto.
- **TanStack Query**: peticiones al backend, caché y refresco automático de los datos, como el estado de las visitas.
- **Axios**: cliente HTTP que añade el token a cada petición y renueva la sesión cuando caduca.
- **React Hook Form + Zod**: formularios y validación de datos, como el check-in, el checklist y los perfiles.
- **date-fns**: manejo de fechas y horas del cuadrante y de las entradas y salidas.
- **Lucide React**: iconos de la interfaz.
- **vite-plugin-pwa**: instalar la aplicación en el móvil como una app y recibir notificaciones.

### 2.2 Backend (Node.js + Express)

#### Autenticación y roles

Se necesita autenticación de cada usuario, ya que la aplicación maneja datos personales y de salud. Hay tres roles diferentes (coordinador, cuidador y familiar) con permisos distintos dentro de la aplicación. Un middleware comprueba el rol en cada ruta, de forma que cada persona solo accede a lo que le corresponde.

Para la autenticación se utilizará JWT con un access token corto y un refresh token en una cookie `httpOnly`. Esta combinación permite una sesión larga, importante para que el familiar no tenga que meter la contraseña cada vez. Las contraseñas se guardan cifradas con bcrypt. Para leer la cookie se usa `cookie-parser`, y para generar y verificar los tokens, `jsonwebtoken`.

#### API externa

Como API externa, únicamente vamos a utilizar OpenRouteService, con el objetivo de calcular cuánto tarda un trabajador entre domicilios, según el tipo de transporte que utilice, y de ordenar los candidatos a una sustitución por tiempo de viaje. La clave de la API se guarda en el servidor, nunca en el frontend.

Si el servicio falla o se agota su límite gratuito, el sistema usará una estimación propia con la fórmula de Haversine, que calcula la distancia más corta sobre la superficie de una esfera (como la Tierra) entre dos puntos definidos por su latitud y longitud.

| Servicio | Uso | Límite gratuito |
|---|---|---|
| OpenRouteService | Tiempos de viaje entre domicilios | Más de 500 peticiones al día y 40 por minuto (requiere API key gratuita) |

#### Otras bibliotecas necesarias

- **Express**: servidor y rutas de la API.
- **Mongoose**: conexión con MongoDB y definición de los esquemas.
- **dotenv**: variables de entorno, como la clave de ORS y los secretos de JWT.
- **cors**: permitir las peticiones desde el dominio del frontend.
- **helmet**: cabeceras HTTP de seguridad.
- **express-rate-limit**: limitar las peticiones y proteger el login y la cuota de OpenRouteService.
- **Zod**: validar los datos que llegan a la API.
- **web-push**: enviar notificaciones push a los móviles sin depender de un servicio de pago.
- **nodemon**: reiniciar el servidor al guardar cambios durante el desarrollo.

### 2.3 Base de datos (MongoDB)

Hemos pensado en usar cinco colecciones principales: `users`, `assistedPersons`, `visits`, `substitutionRequests` y `notifications`. Cada colección representa una entidad del problema, y las relaciones entre ellas se hacen con referencias por `_id`.


#### Colecciones

La colección **users** almacena a las tres clases de personas que usan la aplicación (coordinadores, cuidadores y familiares) en un único lugar, diferenciadas por el campo `rol`. Esto simplifica la autenticación, porque todos inician sesión contra la misma colección, y permite aplicar los permisos según el rol. Los datos propios de los cuidadores (experiencia, formación, si pueden usar grúa, si tienen alergia a mascotas y su medio de transporte) van embebidos en el subdocumento `perfilCuidador`, que solo existe para ese rol. En esta colección también se guardan el hash de la contraseña (nunca la contraseña en claro) y los tokens necesarios para enviar notificaciones push.

La colección **assistedPersons** contiene la ficha de cada persona atendida: dirección, ubicación, grado de dependencia, movilidad, patologías, alergias, dieta, medicación y notas. La medicación va embebida como lista, porque siempre se consulta junto a la ficha. Esta colección se relaciona con `users` mediante `cuidadorTitularId` (un cuidador titular) y mediante `familiaresIds` (uno o varios familiares autorizados). Esta segunda referencia define qué datos puede ver cada familiar, de modo que solo accede a la información de su propio familiar.

La colección **visits** es la central del sistema, porque cada documento representa un servicio concreto, con su persona atendida, su cuidador y su horario previsto. Su campo `estado` permite seguir el servicio (programada, en curso, completada o cancelada). Las horas reales de llegada y salida se guardan en `checkIn` y `checkOut`, junto a la ubicación. Las tareas realizadas se guardan dentro de la propia visita, ya que el cuidador las marca durante el servicio y la familia las consulta en conjunto. Esta colección sirve de base para el resumen diario de la familia, la monitorización del coordinador y el historial de visitas.

La colección **substitutionRequests** gestiona las bajas y sustituciones. Cuando un cuidador no puede acudir, se crea una solicitud ligada a la visita afectada. En ella se guardan los candidatos a los que se avisó y quién la aceptó. Al cubrirse, la solicitud pasa a estado "cubierta" y se actualiza el `cuidadorId` de la visita. Así se conserva el historial de cambios, que además sirve más adelante para calcular a quién hay que pagar cada servicio.

La colección **notifications** guarda los avisos que reciben las personas, como cambios de horario, sustituciones o alertas. Cada aviso tiene un destinatario, un tipo, un mensaje y un indicador de lectura, y puede ir ligado a una visita. Se guarda en base de datos para que cada usuario pueda consultar su historial aunque no tuviera la aplicación abierta cuando se envió.

#### Esquema preliminar

```text
users
  _id, nombre, email, passwordHash,
  rol: "coordinador" | "cuidador" | "familiar",
  telefono, foto, pushTokens[],
  perfilCuidador: { experiencia, formacion[], puedeUsarGrua, alergiaMascotas,
                    transporte: "coche" | "bicicleta" | "a_pie",
                    ubicacion: { lat, lng } }          (solo cuidadores)

assistedPersons
  _id, nombre, direccion, ubicacion: { lat, lng },
  dependencia, movilidad, patologias[], alergias[], dieta,
  medicacion: [{ nombre, dosis, hora }],
  mascotas, notas,
  cuidadorTitularId -> users,
  familiaresIds[] -> users

visits
  _id, personaId -> assistedPersons, cuidadorId -> users,
  inicioPrevisto, finPrevisto,
  estado: "programada" | "en_curso" | "completada" | "cancelada",
  checkIn: { fecha, lat, lng }, checkOut: { fecha, lat, lng },
  tareas: [{ descripcion, hecha, horaRealizada, observaciones }]

substitutionRequests
  _id, visitId -> visits, solicitadaPor -> users,
  motivo, estado: "abierta" | "cubierta",
  candidatosNotificados[] -> users, aceptadaPor -> users

notifications
  _id, destinatarioId -> users, tipo, mensaje,
  visitId (opcional), leida, createdAt
```

#### Relaciones principales

- Una persona atendida tiene un cuidador titular y varios familiares.
- Una persona atendida tiene muchas visitas, y cada visita pertenece a un solo cuidador.
- Una visita puede tener una solicitud de sustitución.
- Cada usuario puede tener muchas notificaciones.

#### Índices

Se crearán índices en `visits` por `cuidadorId + inicioPrevisto` y por `personaId + inicioPrevisto`, ya que son las consultas más frecuentes (agenda del cuidador y resumen diario).

### 2.4 Infraestructura

**Frontend.** Se desplegará en Vercel, en su capa gratuita, que ofrece despliegue sencillo, CI/CD automático desde GitHub, analíticas de tráfico y mitigación de ataques DDoS.

**Base de datos.** Se usará MongoDB Atlas, que ofrece 512 MB de almacenamiento en su plan gratuito. Es suficiente, ya que solo se almacena texto.

**Backend.** Se desplegará en Render (Web Service gratuito), conectado al repositorio de GitHub. El plan gratuito incluye 750 horas al mes, y el servicio se duerme tras 15 minutos sin tráfico, por lo que la primera petición puede tardar cerca de un minuto. Para mitigarlo se hará un ping periódico a un endpoint `/health`. Render no ofrece disco persistente en el plan gratuito, así que no se guardarán archivos en el servidor.

**Servicios cloud adicionales.** Para el MVP no se necesitan más servicios. Las notificaciones push se envían con `web-push`, sin servicio de pago.
---

## 3. Capacidades del equipo

### 3.1 Inventario de habilidades

| Tecnología | Irene | Dani | Alejandro | Pablo |
|---|:---:|:---:|:---:|:---:|
| HTML y CSS | 4 | 3 | 3 | 3 |
| JavaScript (ES6+, async/await) | 3 | 3 | 2 | 2 |
| React (componentes, hooks, props) | 0 | 2 | 0 | 0 |
| React Router | 0 | 2 | 0 | 0 |
| Tailwind CSS | 3 | 2 | 2 | 2 |
| Vite | 0 | 3 | 0 | 0 |
| TanStack Query | 0 | 0 | 0 | 0 |
| Axios | 0 | 0 | 0 | 0 |
| React Hook Form + Zod | 0 | 0 | 0 | 0 |
| PWA (vite-plugin-pwa) y notificaciones push | 0 | 0 | 0 | 0 |
| Node.js | 1 | 0 | 0 | 0 |
| Express (rutas, middlewares) | 0 | 0 | 0 | 0 |
| Autenticación con JWT (access y refresh token) | 0 | 0 | 0 | 0 |
| bcrypt y seguridad básica (helmet, CORS) | 0 | 0 | 0 | 0 |
| Control de acceso por roles | 2 | 1 | 0 | 0 |
| MongoDB y Mongoose | 1 | 1 | 1 | 1 |
| Diseño de esquemas e índices | 4 | 2 | 2 | 3 |
| Consumo de APIs externas (OpenRouteService) | 3 | 3 | 3 | 3 |
| Git y GitHub (ramas, PR, review) | 5 | 3 | 3 | 3 |
| Despliegue (Vercel, Render, Atlas) | 1 | 2 | 1 | 1 |
| Testing (opcional) | 3 | 4 | 0 | 0 |

---

### 3.2 Lagunas de conocimiento

| Tecnología o tema | Quién la desconoce | Qué hay que aprender | Cómo y cuándo se aprende | Tiempo estimado |
|---|---|---|---|:---:|
| PWA y notificaciones push | Irene, Pablo, Alejandro | Service Workers y suscripción push | Documentación oficial y spike técnico en sprint 2 | 8 h |
| React Hook Form + Zod | Irene, Pablo, Alejandro, Dani | Validación de esquemas en formularios | Mini-módulo de autenticación en semana 1 | 5 h |
| Control de roles con JWT | Irene, Pablo, Alejandro, Dani | Middleware de autorización en Express | Integración de endpoints protegidos en sprint 1 | 6 h |
| OpenRouteService | Irene, Pablo, Alejandro, Dani | Consumo de API REST y cálculo de rutas | Pruebas de integración previas al cuadrante | 4 h |

---

#### Valoración
- ¿Las horas estimadas caben en las horas disponibles?: Sí. El alcance planteado para el MVP es totalmente asumible dentro del tiempo previsto. La carga de trabajo se distribuye de manera equilibrada y no supera la disponibilidad global, permitiendo absorber los tiempos de aprendizaje.

#### Recortes del MVP
- No es necesario aplicar ningún recorte. La planificación temporal y la capacidad del equipo permiten abordar la totalidad de las funcionalidades definidas para el MVP.
- Se desarrolla el 100% del alcance comprometido:
  - Gestión integral de cuadrantes y perfiles de usuarios asistidos (CU-C1, CU-C3).
  - Circuito de sustituciones y sistema de notificaciones (CU-C4, CU-C5, CU-T2).
  - Interfaz de trabajo del cuidador con agenda, check-in/out y checklist (CU-T1, CU-T3, CU-T5, CU-T6).
  - Panel de monitorización en tiempo real para coordinación (CU-C6).
  - Módulo de resumen diario y seguimiento para familiares (CU-F1).
    
---

## 4. Riesgos técnicos

### 4.1 Listado de riesgos
A continuación, se identifican los principales riesgos que podrían afectar al desarrollo, rendimiento o adopción del sistema:

1. **Problemas de conectividad:** Pérdida de conexión o falta de cobertura de red móvil durante el check-in/check-out y completado de tareas por parte de los cuidadores dentro de los domicilios.
2. **Dependencia de terceros (APIs):** Retrasos o fallos en la integración con servicios de geolocalización o mapas (como OpenRouteService).
3. **Cuellos de botella en el servidor:** Sobrecarga del backend (Node.js) ante picos de avisos masivos, como el envío simultáneo de notificaciones por bajas y sustituciones.
4. **Adopción por parte del usuario:** Resistencia al uso de la aplicación por parte de cuidadores con menor destreza o brecha digital.
5. **Desviación de plazos (Scope creep):** Retrasos en el desarrollo provocados por cambios o ampliación de alcance en los requisitos por parte del equipo de coordinación.

### 4.2 Estrategias de mitigación
Para cada riesgo identificado, se aplicarán las siguientes medidas preventivas antes de que ocurran:

| Riesgo | Estrategia de Mitigación |
| :--- | :--- |
| **Problemas de conectividad** | Implementar almacenamiento local en el frontend (mediante capacidades PWA/Service Workers) para que los fichajes y checklists se guarden temporalmente en el dispositivo y se sincronicen automáticamente con la base de datos al recuperar la cobertura. |
| **Dependencia de APIs de mapas** | Seleccionar APIs estables con SDKs probados y desarrollar una capa de abstracción temprana en el código. Esto nos permitirá cambiar rápidamente a un proveedor alternativo (o usar la fórmula de Haversine nativa) si surgen limitaciones, caídas o costes inesperados. |
| **Sobrecarga del backend** | Utilizar un sistema de colas de mensajes (como Redis o similar) para encolar y procesar las notificaciones push masivas de forma asíncrona. Esto evitará bloqueos en el hilo principal del servidor y asegurará la disponibilidad del sistema. |
| **Resistencia al uso (brecha digital)** | Diseñar una interfaz orientada a móviles extremadamente simplificada, con textos grandes y botones claros. Se complementará realizando sesiones de formación práctica con los cuidadores previas al despliegue oficial. |
| **Desviaciones en los plazos** | Establecer un MVP con alcance cerrado y estricto. Se aplicarán metodologías ágiles con iteraciones cortas para validar tempranamente cada funcionalidad con los coordinadores antes de avanzar, bloqueando la entrada de nuevas peticiones funcionales hasta la siguiente fase. |
