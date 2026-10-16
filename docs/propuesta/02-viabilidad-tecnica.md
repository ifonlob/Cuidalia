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

### Must have (Debe tener)
Funciones críticas y obligatorias. Sin ellas, los recorridos mínimos del MVP (gestión de la baja, fichaje y resumen del familiar) no se pueden completar.

- **Autenticación y persistencia de sesión:** El sistema permite el acceso seguro mediante credenciales (JWT), dirigiendo a cada usuario (Coordinador, Cuidador, Familiar) a su interfaz correspondiente y manteniendo la sesión abierta para evitar logins constantes.
- **Cuadrante y filtrado de turnos:** El coordinador puede visualizar los turnos, buscar por trabajador y filtrar aquellos afectados por una baja para identificar rápidamente qué servicios necesitan un sustituto.
- **Gestión de sustituciones in-app:** El coordinador puede seleccionar un turno sin cubrir, elegir a un trabajador disponible y asignarle el servicio, permitiendo que el trabajador lo reciba y acepte directamente desde su aplicación móvil.
- **Fichaje geolocalizado con tolerancia offline:** El cuidador puede registrar su entrada (check-in) y salida (check-out) en el domicilio. El sistema valida la cobertura y, si falla, guarda el registro localmente para sincronizarlo cuando recupere la conexión.
- **Checklist de tareas interactivas:** El cuidador visualiza un listado de tareas específicas del usuario asignado (medicación, aseo) y las marca como completadas durante el servicio, validando automáticamente la información al terminar.
- **Resumen diario automatizado:** El sistema genera un reporte a partir del checklist del cuidador y envía una notificación push al familiar indicando que el servicio ha finalizado. El familiar entra a la app y visualiza este resumen para comprobar que todo ha ido bien.

### Should have (Debería tener)
Funciones que mejoran enormemente la experiencia, pero cuyo desarrollo podría aplazarse si hay riesgos de tiempo, ya que el happy path del MVP puede funcionar sin ellas.

- **Gestión y reporte de incidencias:** El cuidador puede registrar desde su app cualquier anomalía ocurrida durante el turno (negativas a medicación, falta de material) y el coordinador puede visualizarla, priorizarla y hacerle seguimiento.
- **Monitorización de visitas en tiempo real:** El coordinador dispone de un panel de alertas donde ve de forma automática quién ha hecho check-in, quién se retrasa o quién no ha aparecido, sin tener que revisar el cuadrante celda por celda.
- **Filtros avanzados por perfil y distancia:** Al buscar un sustituto, el coordinador puede filtrar a los cuidadores según las necesidades del paciente (uso de grúa, alergias) y ordenarlos por tiempo de desplazamiento utilizando la API de OpenRouteService (o la fórmula de Haversine).
- **Alertas inmediatas de gravedad:** El sistema puede enviar notificaciones push destacadas al familiar y al coordinador en caso de que el cuidador reporte un evento grave, como una caída o un mareo.
- **Notificaciones preventivas de cambios:** Envío de avisos automáticos a las familias cuando se cambia al trabajador titular por un sustituto, mostrando el perfil básico del nuevo cuidador.

### Could have (Podría tener)
Funcionalidades deseables, pero que están claramente fuera del alcance del MVP inicial y se abordarán en futuras iteraciones.

- **Mensajería interna (Chat centralizado):** Familiares, coordinadores y cuidadores pueden comunicarse mediante un chat integrado en la plataforma, eliminando el uso de WhatsApp y centralizando la información.
- **Solicitudes directas de la familia:** El familiar puede pedir adelantar una visita, cambiar un horario o añadir una tarea puntual (ej. aplicar una crema) a través de un formulario en la app, y ver el estado de aprobación de su solicitud.
- **Botón de emergencia (SOS):** Un acceso rápido en la app del cuidador que avisa simultáneamente a la familia y a coordinación ante una urgencia, mostrando los teléfonos médicos pertinentes.
- **Generador de informes para nóminas:** El sistema calcula de manera automatizada las horas mensuales trabajadas y las sustituciones realizadas por cada empleado para exportarlas a gestión laboral.

### Won't have (No tendrá)
Límites claros del proyecto. Lo que el sistema NO va a hacer en esta versión.

- **Generación automática o inteligente de cuadrantes:** El sistema no utilizará Inteligencia Artificial ni algoritmos complejos para crear los horarios mensuales desde cero, ya que la creación y edición inicial de los servicios seguirá siendo manual por parte del coordinador.
- **Pasarela de pagos y facturación:** La aplicación no gestionará cobros a las familias mediante tarjeta de crédito ni calculará importes económicos de facturas; se limitará a la gestión de tiempos y tareas.
- **Integración con sistemas de salud públicos:** La aplicación operará de forma aislada y no se conectará con el historial clínico electrónico de la comunidad autónoma ni con bases de datos de hospitales.
- **Videollamadas integradas:** Toda la comunicación dentro de la app se realizará mediante texto (resúmenes, notificaciones o chat en un futuro), descartando funcionalidades de streaming de vídeo entre familias y cuidadores.

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

- **React Router**: permitirá ir cambiando entre apartados sin necesidad de recargar la página en el navegador; además gestiona las rutas protegidas dependiendo del rol que tenga el usuario.
- **Tailwind CSS**: facilitará la creación de interfaces capaces de responder al usuario y mantener un sistema de diseño moderno y constante.
- **Vite**: aportará un servidor de desarrollo capaz de recargar muy rápido los módulos, compilar, optimizar y reducir el tamaño de los archivos; en definitiva, reducirá los tiempos de manera significativa.
- **TanStack Query**: llevará a cabo las peticiones, almacenaje en cache de datos que llegan de la base de datos, gestionará cargas y validará datos en segundo plano evitando sobrecargar la API de llamadas.
- **Axios**: ejecutará peticiones HTTP, configurará interceptores que inyectarán tokens, transformará respuestas y capturará errores tipo de 401, 403.
- **React Hook Form + Zod**: gestionará campos evitando renderizados innecesarios en la interfaz, por su parte, Zod definirá esquemas de validación. Juntos se encargarán de que no se envién datos erróneos al servidor y de mostrar los errores de forma clara para una comprensión de calidad.
- **date-fns**: gestionará datos como el horario y los registros además de formatearlos.
- **Lucide React**: proporcionará iconos y calidad visual a la interfaz, mejorando la accesibilidad.
- **vite-plugin-pwa**: configurará el manifiesto web y los Service Workers para que los usuarios puedan instalar la app en sus dispositivos simulando una aplicación nativa además de habilitar la carga de recursos sin conexión a internet.

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

### 3.2 Lagunas de conocimiento

Después de revisar lo que sabe cada miembro del equipo y lo que necesita el proyecto inicial (MVP), hemos detectado qué cosas nos faltan por aprender. Para asegurarnos de que llegamos a tiempo, hemos decidido que no todos vamos a aprender de todo al mismo nivel (nos repartiremos el trabajo) y pondremos un límite máximo de horas para investigar los temas menos urgentes.

| Tecnología o tema | Quién lo desconoce | Qué hay que aprender exactamente | Cómo y cuándo se va a aprender | Tiempo estimado |
|---|---|---|---|:---:|
| **App instalable y notificaciones (PWA)** | Irene, Dani, Alejandro, Pablo | Cómo instalar la web como si fuera una app en el móvil y cómo enviar avisos (notificaciones). | Prueba rápida con tiempo máximo estricto en el segundo sprint. | 4 h |
| **Formularios seguros (React Hook Form + Zod)** | Irene, Dani, Alejandro, Pablo | Cómo asegurar que los datos que escriben los usuarios no tienen errores (al fichar o crear perfiles). | Creando una pequeña pantalla de prueba la primera semana. | 5 h |
| **Control de usuarios y permisos (JWT)** | Irene, Dani, Alejandro, Pablo | Cómo controlar quién entra a la app y asegurar que un familiar no vea los datos de otro paciente. | Mientras creamos el sistema de inicio de sesión en el primer sprint. | 6 h |
| **Cálculo de distancias (OpenRouteService)** | Equipo al completo | Cómo conectar la app con un mapa para calcular cuánto tarda un cuidador en llegar a una casa. | Límite de 2 horas de prueba en el segundo sprint (si falla, usaremos una fórmula matemática más sencilla). | 2 h |
| **Creación de pantallas (React y herramientas)** | Irene, Alejandro, Pablo | Cómo construir las vistas de la aplicación y conectarlas con los datos de forma fluida. | Copiando la estructura base que hará el compañero con más experiencia (Dani) la primera semana. | 8 h |
| **Cerebro de la aplicación (Node y Express)** | Irene, Dani, Alejandro, Pablo | Cómo recibir las peticiones de los usuarios (como pedir ver un perfil) y responder de forma segura. | Programando en parejas al montar la base del proyecto en el primer sprint. | 6 h |
| **Base de datos (MongoDB)** | Irene, Dani, Alejandro, Pablo | Cómo guardar, buscar, actualizar y borrar la información básica sin complicarnos. | En una reunión conjunta para diseñar cómo guardar los datos la primera semana. | 5 h |

**Total de horas destinadas a aprendizaje/investigación:** 36 horas. 

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
