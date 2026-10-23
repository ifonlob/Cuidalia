# Viabilidad técnica

## Introducción
En este apartado se analiza la viabilidad técnica del proyecto, evaluando las tecnologías necesarias para desarrollar el MVP, las capacidades del equipo, la infraestructura disponible y los principales riesgos técnicos. El objetivo es determinar si es posible implementar las funcionalidades prioritarias dentro del plazo previsto y con los recursos disponibles.
---

## 1. Funcionalidades previstas por perfil

Los siguientes apartados describen la visión funcional global de CUIDALIA y agrupan las necesidades por perfil. No todas estas funciones forman parte del MVP. La lista oficial de requisitos funcionales priorizados es la tabla MoSCoW del apartado 4, y el alcance obligatorio de esta versión se concreta en el apartado 5.

### 1. Persona principal: Coordinador/a
#### Gestionar el cuadrante de horarios
En la versión completa, el coordinador podrá crear y modificar los horarios de usuarios y trabajadores desde una vista que muestre disponibilidades, vacaciones y huecos libres. En el MVP se consultarán turnos de prueba ya registrados, destacando que la creación y modificación manual de cuadrantes queda como ampliación posterior.

#### Asignar un trabajador a un usuario
En la visión a largo plazo de CUIDALIA, el coordinador podrá comparar cuidadores mediante distintos criterios de compatibilidad. En el MVP, la selección se limitará a comprobar la disponibilidad y la ausencia de conflictos horarios, es decir, los demás criterios se reservan para futuras iteraciones:

- Fuerza para usar grúa.
- Experiencia en demencias.
- Alergias a mascotas.
- Baño adaptado.
- Carácter.
- Distancia al domicilio.

Esto reduce los emparejamientos fallidos, que obligan a empezar de cero.

#### Gestionar el perfil del usuario
El coordinador registra y actualiza la siguiente información:

- Grado de dependencia.
- Necesidad de aseo en cama.
- Medicación.
- Horario contratado.
- Contactos de la familia.

Toda esa información queda en un único lugar, en vez de repartida entre papel, Excel y WhatsApp.

#### Gestionar bajas y sustituciones
Cuando un trabajador no puede acudir, la persona coordinadora consulta los trabajadores disponibles, selecciona un candidato válido y le envía una propuesta de sustitución. El trabajador puede consultar la propuesta y aceptarla desde su interfaz. Una vez aceptada, la aplicación actualiza el estado del servicio para que coordinación pueda comprobar que la sustitución está cubierta.

En el MVP no se enviarán avisos simultáneos a varios cuidadores ni se asignará automáticamente el servicio a la primera persona que acepte.

#### Notificar cambios a familia y cuidadores
En una versión posterior, el sistema podrá avisar automáticamente de los cambios de horario o de trabajador. En el MVP, la confirmación de la sustitución quedará visible en la aplicación para la persona coordinadora, en donde las notificaciones automáticas se reservan para una ampliación.

#### Monitorizar las visitas en tiempo real
En una versión posterior, el coordinador podrá consultar quién ha llegado, quién se retrasa y quién no se ha presentado mediante un panel de seguimiento y alertas. La monitorización en tiempo real no forma parte del MVP.

#### Gestionar incidencias
El coordinador registra, prioriza y hace seguimiento de las incidencias, como:

- Bajas.
- Síntomas extraños.
- Cambios por citas médicas.
- Malas noches.

Todas quedan documentadas y no solo comunicadas por teléfono.

#### Consultar ubicación y huecos de los trabajadores
Como ampliación, el coordinador podrá consultar la ubicación de los trabajadores y sus huecos disponibles. La geolocalización en tiempo real no es necesaria para completar el MVP. Además, la selección inicial se basará en la disponibilidad y los conflictos horarios registrados.

#### Generar el informe de horas para nóminas
El sistema calcula las horas trabajadas y las sustituciones del mes.

Desaparecen los post-its y los colores en Excel.

#### Revisar el historial de tareas
En una versión posterior, el coordinador podrá consultar el historial de tareas realizadas en cada visita. El MVP no incluye el registro completo de tareas ni la consulta de su historial.

#### Comunicarse por mensajería interna
Como ampliación posterior, el coordinador podrá comunicarse con familiares y cuidadores mediante un canal interno. El chat centralizado no forma parte del MVP.

---

### 2. Persona secundaria 1: Familiar
#### Consultar el resumen diario de tareas
En una versión posterior, el familiar podrá abrir la aplicación y consultar de un vistazo:

- Medicación.
- Comida.
- Aseo.
- Cómo ha dormido su familiar.
- Su estado de ánimo.

Así no tiene que llamar a la oficina ni esperar a la tarde para saberlo.

#### Recibir alertas inmediatas
En una versión posterior, el familiar podrá recibir una notificación destacada cuando se registre una incidencia relevante. Las alertas push no forman parte del MVP.

#### Solicitar cambios o necesidades
Como ampliación posterior, el familiar podrá solicitar cambios o tareas puntuales y consultar el estado de la solicitud. Esta funcionalidad no se implementará en el MVP.

#### Conocer al cuidador sustituto
En una versión posterior, el familiar podrá recibir información autorizada sobre el trabajador sustituto. Los avisos automáticos y la ficha ampliada del sustituto quedan fuera del MVP.

#### Chatear con coordinación o con el cuidador
En una versión posterior, el familiar podrá comunicarse con coordinación o con el cuidador mediante un chat interno. Esta opción queda fuera del MVP.

#### Consultar el calendario de visitas
En una versión posterior, el familiar podrá consultar el calendario de visitas. Esta vista no es necesaria para completar el MVP.

#### Usar la app cómodamente desde el móvil
La interfaz es visual, con pocos menús y sesión persistente, porque el familiar dispone de poco tiempo.

---

### 3. Persona secundaria 2: Cuidador/a
#### Consultar la agenda personal
En una versión posterior, el cuidador podrá consultar su agenda, direcciones y horarios, y recibir avisos de cambios. En el MVP solo necesita consultar la sustitución que se le haya asignado y aceptar el turno.

#### Avisar de que no puede acudir
En una versión posterior, el cuidador podrá comunicar una baja desde la aplicación. En el MVP, el recorrido parte de una baja registrada como dato de prueba y se centra en gestionar su sustitución.

#### Ver el perfil del usuario
En una versión posterior, el cuidador podrá consultar la información pertinente de la persona atendida antes de una visita, especialmente cuando se trate de una sustitución:

- Movilidad.
- Patologías.
- Alergias.
- Mascotas.
- Medicación.
- Dieta.

#### Consultar notas y rutinas del usuario
Como ampliación, el cuidador podrá consultar rutinas, preferencias y observaciones operativas relevantes para facilitar la continuidad entre visitas. Este resumen contextual no forma parte del MVP.

#### Registrar llegada y salida
En una versión posterior, el cuidador podrá registrar la entrada y salida del domicilio mediante fichaje, con una posible validación geolocalizada. El fichaje no forma parte del MVP.

#### Marcar las tareas realizadas
En una versión posterior, el cuidador podrá completar una lista de tareas específicas para cada servicio. El checklist no forma parte del MVP.

#### Reportar incidencias
En una versión posterior, el cuidador podrá registrar incidencias del servicio, como tareas rechazadas, caídas, falta de material o peticiones fuera del plan. El registro de incidencias no forma parte del MVP.

#### Activar un botón de emergencia
Como ampliación posterior, se podrá incorporar un acceso SOS que facilite contactar con coordinación y consultar teléfonos de emergencia. No se implementará en el MVP ni sustituirá a los servicios de emergencia.

#### Recibir avisos de cambios importantes
En una versión posterior, el cuidador podrá recibir avisos sobre cambios importantes y confirmar su lectura. Esta funcionalidad no forma parte del MVP.

---

## 4. Priorización de funcionalidades (MoSCoW)
| Prioridad | Requisito funcional |
|---|---|
| **Must** | Autenticar a coordinadores y trabajadores participantes en el MVP y mostrar las opciones permitidas según su rol (el acceso funcional para familiares se incorporará en una iteración posterior) |
| **Must** | Consultar los turnos programados en una vista de cuadrantes. |
| **Must** | Filtrar los turnos para identificar los servicios afectados por una baja. |
| **Must** | Mostrar trabajadores candidatos y excluir a quienes no estén disponibles o tengan un conflicto horario. |
| **Must** | Asignar un trabajador candidato al servicio afectado y permitir que acepte la sustitución desde su interfaz. |
| **Should** | Crear y modificar manualmente los datos básicos de los turnos desde la interfaz de coordinación. |
| **Should** | Registrar la hora de entrada y salida del trabajador en un servicio asignado. |
| **Should** | Mostrar al trabajador una lista de tareas asignadas y guardar cuáles ha completado. |
| **Should** | Generar un resumen del servicio a partir de las tareas registradas y permitir que lo consulte el familiar autorizado. |
| **Could** | Enviar notificaciones push sobre cambios de turno o sustituciones, siempre que se confirme su viabilidad en los dispositivos objetivo. |
| **Could** | Generar un resumen contextual de la visita anterior con tareas pendientes, incidencias abiertas, rutinas y observaciones relevantes para el siguiente profesional (*CUIDALIA Continuidad*). |
| **Could** | Detectar repeticiones en tareas pendientes o incidencias mediante reglas configurables y mostrar los registros que justifican cada aviso. |
| **Could** | Comparar profesionales según criterios de compatibilidad explicables y, si resulta viable, estimar las distancias o los tiempos de desplazamiento, como ampliación posterior al MVP. |
| **Could** | Registrar el grado de ayuda prestada en actividades cotidianas para reflejar la participación de la persona atendida (*CUIDALIA Autonomía*). |
| **Could** | Incorporar un chat interno para que coordinación, profesionales y familiares autorizados puedan intercambiar mensajes. |
| **Could** | Permitir que los familiares envíen solicitudes de cambios o tareas adicionales y consulten su estado. |
| **Could** | Añadir un botón SOS que facilite avisar a coordinación y consultar los teléfonos de emergencia, sin sustituir a los servicios de emergencia. |
| **Could** | Generar un informe mensual de las horas registradas y de las sustituciones, con opción de exportación para revisión administrativa. |
| **Won't** | Generar automáticamente cuadrantes mensuales mediante inteligencia artificial o un algoritmo complejo de planificación. |
| **Won't** | Gestionar pagos o facturación económica, integrarse con historiales clínicos de la sanidad pública o incorporar videollamadas. |

### Justificación de las prioridades
- **Must:** constituyen el recorrido mínimo de sustitución. Consulta y filtrado de turnos, validación de disponibilidad, asignación y aceptación, el problema principal no queda resuelto.
- **Should:** amplían el producto hacia la gestión cotidiana de los servicios edición de turnos, fichaje, checklist y resumen familiar, pero no son imprescindibles para demostrar que una baja puede cubrirse correctamente.
- **Could:** se valorarán después de completar el MVP. Incluyen notificaciones, las funcionalidades diferenciales de CUIDALIA y otras herramientas complementarias.
- **Won't:** quedan explícitamente fuera de esta versión para contener la complejidad y concentrar el esfuerzo del equipo en el recorrido principal.

---

## 5. Producto Mínimo Viable (MVP)
### 5.1. Recorrido principal: gestionar una baja y completar una sustitución
**Objetivo:** permitir que la persona coordinadora cubra un servicio afectado por la baja de un trabajador y compruebe que el sustituto seleccionado ha aceptado el turno.

El MVP se limitará a este recorrido completo. El trabajador intervendrá únicamente en las acciones necesarias para consultar y aceptar la sustitución. No se exigirán tres recorridos completos (coordinación, trabajador y familiar) en la primera versión.

1. La persona coordinadora inicia sesión y accede a la vista de **Cuadrantes**.
2. Consulta los turnos programados y filtra los servicios afectados por la baja.
3. Selecciona el servicio que necesita cobertura.
4. Consulta la lista de trabajadores candidatos disponibles.
5. El sistema excluye de la lista a los trabajadores no disponibles o con conflictos de horario, según los datos de prueba registrados.
6. La persona coordinadora selecciona un candidato y confirma la asignación de la sustitución.
7. El trabajador entra en su interfaz móvil, consulta la sustitución pendiente y la acepta.
8. El sistema actualiza el estado de la sustitución y muestra la confirmación a la persona coordinadora.

**Regla de asignación del MVP:** la persona coordinadora elige directamente a un trabajador de la lista de candidatos válidos. No se desarrollará en esta versión un sistema que envíe avisos simultáneos a varios trabajadores y asigne automáticamente el servicio al primero que lo acepte. Esta decisión evita la contradicción entre los requisitos funcionales y el recorrido que se había descrito previamente.

### 5.2. Funcionalidades incluidas
El recorrido se desarrollará con los cinco requisitos *Must*:

- Autenticación y acceso según el rol.
- Consulta de turnos programados.
- Filtrado de servicios afectados por una baja.
- Consulta de candidatos con validación básica de disponibilidad y conflictos horarios.
- Asignación de la sustitución, aceptación por el trabajador y actualización del estado.

Para que el flujo sea demostrable dentro del tiempo del módulo, se utilizarán datos ficticios de turnos, trabajadores y disponibilidades. La creación avanzada de cuadrantes no es necesaria para esta demostración: el recorrido parte de servicios de prueba que ya existen en la base de datos.

### 5.3. Funcionalidades fuera del núcleo del MVP
Las siguientes funciones no serán requisitos de finalización del MVP, aunque se mantienen como prioridades para iteraciones posteriores:

- Fichaje de entrada y salida, incluida la geolocalización.
- Checklist de tareas y registro completo de su realización.
- Resumen diario y portal funcional para familiares.
- Notificaciones push, monitorización en tiempo real y alertas de retraso.
- Chat interno, solicitudes familiares y botón SOS.
- Optimización avanzada de rutas, puntuación ponderada de compatibilidad y detección de patrones.
- Registro de autonomía y generación de informes de horas para nóminas.

El trabajo del trabajador se limita en el MVP a consultar y aceptar el turno de sustitución. El familiar no necesita completar un recorrido dentro de esta primera versión. Su interfaz y el resumen diario se incorporarán cuando el flujo de sustitución esté terminado y probado.

### 5.4. Criterios de aceptación del MVP
El MVP se considerará completado cuando se pueda demostrar que:

1. Un usuario puede iniciar sesión y solo acceder a las opciones correspondientes a su rol.
2. Coordinación puede localizar un servicio afectado por una baja en la vista de cuadrantes.
3. El sistema no permite seleccionar como candidato válido a un trabajador no disponible o con conflicto horario.
4. Coordinación puede asignar un trabajador válido al servicio afectado.
5. El trabajador puede aceptar la sustitución y el estado actualizado queda visible para coordinación.
6. El recorrido se puede realizar de principio a fin con datos de prueba, sin modificar manualmente la base de datos durante la demostración.

La usabilidad del recorrido se medirá antes de la defensa final mediante cinco escenarios cronometrados. El objetivo será completar la identificación y asignación de un candidato válido en un máximo de tres minutos y seis acciones principales de interfaz en, al menos, cuatro de los cinco escenarios. La aceptación del trabajador se evaluará aparte: deberá completarse en menos de un minuto en, al menos, cuatro de cinco pruebas.

Estos valores son criterios previstos de éxito, no resultados ya obtenidos.

---

## 6. Resumen de los perfiles y sus objetivos
| Perfil | Participación en el MVP | Evolución prevista |
|---|---|---|
| **Coordinador/a** | Gestiona la baja, consulta candidatos y asigna una sustitución. | Consultar el contexto de visitas anteriores, patrones explicables y criterios de compatibilidad. |
| **Trabajador/a** | Consulta y acepta la sustitución que se le ha asignado. | Consultar agenda, fichar, registrar tareas e incidencias y utilizar el resumen contextual. |
| **Familiar autorizado** | No tiene un recorrido funcional obligatorio en el MVP inicial. | Consultar resúmenes diarios, cambios relevantes y solicitudes según sus permisos. |

---

## 7. Resumen del alcance del MVP
El MVP se concentrará en **un único recorrido principal y completo: la gestión de una baja y la aceptación de su sustitución**. Incluirá autenticación por roles, consulta y filtrado de turnos, validación básica de disponibilidad, asignación de un trabajador y confirmación de aceptación.

El fichaje, el checklist de tareas y el resumen familiar seguirán formando parte de la hoja de ruta, pero no se exigirán para dar por terminado el MVP. Una vez que el recorrido principal esté implementado, integrado y probado, se valorarán la incorporación de las funcionalidades *Should* según el tiempo restante.

Esta delimitación permite priorizar un flujo funcional y comprobable en lugar de repartir el esfuerzo entre varias experiencias incompletas. También deja espacio para validar posteriormente la propuesta de valor diferencial de CUIDALIA: conectar la información entre visitas, facilitar la revisión de patrones repetidos y explicar los criterios que apoyan las decisiones de coordinación.

---

## 8. Análisis de requisitos técnicos
### 8.1 Frontend (React)
- **React Router**: permitirá ir cambiando entre apartados sin necesidad de recargar la página en el navegador. Además gestiona las rutas protegidas dependiendo del rol que tenga el usuario.
- **Tailwind CSS**: facilitará la creación de interfaces capaces de responder al usuario y mantener un sistema de diseño moderno y constante.
- **Vite**: aportará un servidor de desarrollo capaz de recargar muy rápido los módulos, compilar, optimizar y reducir el tamaño de los archivos. En definitiva, reducirá los tiempos de manera significativa.
- **TanStack Query**: llevará a cabo las peticiones, almacenaje en cache de datos que llegan de la base de datos, gestionará cargas y validará datos en segundo plano evitando sobrecargar la API de llamadas.
- **Axios**: ejecutará peticiones HTTP, configurará interceptores que inyectarán tokens, transformará respuestas y capturará errores tipo de 401, 403.
- **React Hook Form + Zod**: gestionará campos evitando renderizados innecesarios en la interfaz, por su parte, Zod definirá esquemas de validación. Juntos se encargarán de que no se envién datos erróneos al servidor y de mostrar los errores de forma clara para una comprensión de calidad.
- **date-fns**: gestionará datos como el horario y los registros además de formatearlos.
- **Lucide React**: proporcionará iconos y calidad visual a la interfaz, mejorando la accesibilidad.
- **vite-plugin-pwa**: configurará el manifiesto web y los Service Workers para que los usuarios puedan instalar la app en sus dispositivos simulando una aplicación nativa además de habilitar la carga de recursos sin conexión a internet.

### 8.2 Backend (Node.js + Express)
#### Autenticación y roles
Se necesita autenticación para proteger el acceso a la aplicación. En el MVP se implementarán los roles de coordinador y cuidador, con permisos diferenciados comprobados mediante middleware en cada ruta. El rol familiar forma parte del diseño global y se habilitará cuando se desarrolle su interfaz en una iteración posterior.

Para la autenticación se utilizará JWT con un access token corto y un refresh token en una cookie `httpOnly`. Esta combinación permite una sesión larga, importante para que el familiar no tenga que meter la contraseña cada vez. Las contraseñas se guardan cifradas con bcrypt. Para leer la cookie se usa `cookie-parser`, y para generar y verificar los tokens, `jsonwebtoken`.

#### API externa
OpenRouteService se reserva para una posible ampliación del sistema, con el objetivo de estimar tiempos de desplazamiento y ayudar a comparar candidatos por distancia o ruta. Esta integración no es necesaria para completar el MVP, que seleccionará candidatos según la disponibilidad y los conflictos horarios registrados. Si se incorpora posteriormente y el servicio falla o se agota su cuota, podrá utilizarse Haversine como estimación de distancia en línea recta entre dos coordenadas. La clave de la API se guardará en el servidor, nunca en el frontend.

| Servicio | Uso | Límite gratuito |
|---|---|---|
| OpenRouteService | Cálculo opcional de distancias o tiempos de viaje en una iteración posterior | El límite depende del endpoint elegido y deberá comprobarse antes de integrar el servicio |

#### Otras bibliotecas necesarias
- **Express**: recibirá las solicitudes entrantes, ejecutará middlewares(puentes) y devolverá respuestas con una estructura.
- **Mongoose**: funcionará como ODM para modelar y tipar documentos de la BD NoSQL, se asegurara de cumplir validaciones antes de guardar datos.
- **dotenv**: cargara con seguridad credenciales sensibles, rutas y puertos asegurandose así de mantener una seguridad y evitar filtraciones a publico no deseado.
- **cors**: permitirá peticiones HTTP a la API sin bloqueos por seguridad y rechazara las que no estén autorizadas, controla la política de Intercambio de Recursos de Origen Cruzado.
- **helmet**: aplica de manera automática  encabezados de seguridad para mitigar vulnerabilidades web tìpicas.
- **express-rate-limit**: limitar las peticiones y proteger el login y la cuota de OpenRouteService.
- **Zod**: comprueba en el backend que los cuerpos de las peticiones, parámetros y consultas cumplen con los estándares antes de que sean procesados devolviendo errores muy descriptivos.
- **web-push**: implementa estándares Web Push a partir de protocolos VAPID que derivan alertas al Service Worker, manteniendo operativas las alertas incluso cuando la app esta cerrada en primer plano.
- **nodemon**: mejora la productividad en local al monitorizar los archivos backend y reiniciar procesos.

### 8.3 Base de datos (MongoDB)
Hemos pensado en usar cinco colecciones principales: `users`, `assistedPersons`, `visits`, `substitutionRequests` y `notifications`. Cada colección representa una entidad del problema, y las relaciones entre ellas se hacen con referencias por `_id`.

#### Colecciones
La colección **users** almacena a las tres clases de personas que usan la aplicación (coordinadores, cuidadores y familiares) en un único lugar, diferenciadas por el campo `rol`. Esto simplifica la autenticación, porque todos inician sesión contra la misma colección, y permite aplicar los permisos según el rol. Los datos propios de los cuidadores (experiencia, formación, si pueden usar grúa, si tienen alergia a mascotas y su medio de transporte) van embebidos en el subdocumento `perfilCuidador`, que solo existe para ese rol. En esta colección también se guardan el hash de la contraseña (nunca la contraseña en claro) y los tokens necesarios para enviar notificaciones push.

La colección **assistedPersons** contiene la ficha de cada persona atendida: dirección, ubicación, grado de dependencia, movilidad, patologías, alergias, dieta, medicación y notas. La medicación va embebida como lista, porque siempre se consulta junto a la ficha. Esta colección se relaciona con `users` mediante `cuidadorTitularId` (un cuidador titular) y mediante `familiaresIds` (uno o varios familiares autorizados). Esta segunda referencia define qué datos puede ver cada familiar, de modo que solo accede a la información de su propio familiar.

La colección **visits** es la central del sistema, porque cada documento representa un servicio concreto, con su persona atendida, su cuidador y su horario previsto. Su campo `estado` permite seguir el servicio (programada, en curso, completada o cancelada). Las horas reales de llegada y salida se guardan en `checkIn` y `checkOut`, junto a la ubicación. Las tareas realizadas se guardan dentro de la propia visita, ya que el cuidador las marca durante el servicio y la familia las consulta en conjunto. Esta colección sirve de base para el resumen diario de la familia, la monitorización del coordinador y el historial de visitas.

La colección **substitutionRequests** gestiona las bajas y sustituciones. Cada solicitud está ligada a una visita afectada y registra el trabajador propuesto por coordinación, el estado de la solicitud y, cuando corresponde, quién la ha aceptado. Al aceptar el trabajador, la solicitud pasa de "pendiente de aceptación" a "cubierta" y se actualiza el `cuidadorId` de la visita. Así se conserva el historial del cambio. En el MVP se propone un trabajador cada vez, es decir, no se envían avisos simultáneos a una lista de candidatos.

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

   motivo, estado: "pendiente_aceptacion" | "cubierta",

   trabajadorPropuestoId -> users, aceptadaPor -> users

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

### 8.4 Infraestructura
**Frontend.** Se desplegará en Vercel, en su capa gratuita, que ofrece despliegue sencillo, CI/CD automático desde GitHub, analíticas de tráfico y mitigación de ataques DDoS.

**Base de datos.** Se usará MongoDB Atlas, que ofrece 512 MB de almacenamiento en su plan gratuito. Es suficiente, ya que solo se almacena texto.

**Backend.** Se desplegará en Render (Web Service gratuito), conectado al repositorio de GitHub. El plan gratuito incluye 750 horas al mes, y el servicio se duerme tras 15 minutos sin tráfico, por lo que la primera petición puede tardar cerca de un minuto. Para mitigarlo se hará un ping periódico a un endpoint `/health`. Render no ofrece disco persistente en el plan gratuito, así que no se guardarán archivos en el servidor.

**Servicios cloud adicionales.** Para el MVP no se necesitan servicios adicionales ni notificaciones push. Si se incorporan en una iteración posterior, podrán evaluarse las notificaciones web mediante `web-push`, teniendo en cuenta la compatibilidad de los dispositivos objetivo.

---

## 9 Lagunas de conocimiento
Después de revisar lo que sabe cada miembro del equipo y lo que necesita el proyecto inicial (MVP), hemos detectado qué cosas nos faltan por aprender. Para asegurarnos de que llegamos a tiempo, hemos decidido que no todos vamos a aprender de todo al mismo nivel (nos repartiremos el trabajo) y pondremos un límite máximo de horas para investigar los temas menos urgentes.
| Tecnología o tema | Quién lo desconoce | Qué hay que aprender exactamente | Cómo y cuándo se va a aprender | Tiempo estimado |
|---|---|---|---|:---:|
| **App instalable y notificaciones (PWA)** | Irene, Dani, Alejandro, Pablo | Cómo instalar la web como si fuera una app en el móvil y cómo enviar avisos (notificaciones). | Prueba rápida con tiempo máximo estricto en el segundo sprint. | 4 h |
| **Formularios seguros (React Hook Form + Zod)** | Irene, Dani, Alejandro, Pablo | Cómo asegurar que los datos que escriben los usuarios no tienen errores (al fichar o crear perfiles). | Creando una pequeña pantalla de prueba la primera semana. | 5 h |
| **Control de usuarios y permisos (JWT)** | Irene, Dani, Alejandro, Pablo | Cómo controlar quién entra a la app y asegurar que un familiar no vea los datos de otro paciente. | Mientras creamos el sistema de inicio de sesión en el primer sprint. | 6 h |
| **Cálculo de distancias (OpenRouteService)** | Equipo al completo | Cómo integrar, en una futura iteración, un servicio para estimar tiempos de desplazamiento. No es necesario para el MVP, por lo que si se aborda, se limitará la prueba inicial a 2 horas y se usará Haversine como alternativa. | 2 h |
| **Creación de pantallas (React y herramientas)** | Irene, Alejandro, Pablo | Cómo construir las vistas de la aplicación y conectarlas con los datos de forma fluida. | Copiando la estructura base que hará el compañero con más experiencia (Dani) la primera semana. | 8 h |
| **Cerebro de la aplicación (Node y Express)** | Irene, Dani, Alejandro, Pablo | Cómo recibir las peticiones de los usuarios (como pedir ver un perfil) y responder de forma segura. | Programando en parejas al montar la base del proyecto en el primer sprint. | 6 h |
| **Base de datos (MongoDB)** | Irene, Dani, Alejandro, Pablo | Cómo guardar, buscar, actualizar y borrar la información básica sin complicarnos. | En una reunión conjunta para diseñar cómo guardar los datos la primera semana. | 5 h |

**Total de horas destinadas a aprendizaje/investigación:** 36 horas.  

---

#### Valoración
- **¿Las horas estimadas caben en las horas disponibles?:** Inicialmente no. Nuestro primer análisis de conocimientos detectó un desfase importante (necesitábamos más de 50 horas de aprendizaje para un límite de unas 40 horas). Sin embargo, tras aplicar límites de tiempo estrictos y repartirnos los temas en lugar de que todos aprendamos todo, hemos logrado ajustar la formación a 36 horas. Con esta estrategia realista, el alcance del MVP sí es asumible y nos deja un pequeño margen de seguridad.

#### Recortes y ajustes del MVP
- Para asegurar que el proyecto se entrega a tiempo y funciona, sí ha sido necesario aplicar recortes técnicos y metodológicos, priorizando el flujo principal sobre los detalles complejos:

   \- **Simplificación de PWA y notificaciones:** Se ha reducido a lo mínimo funcional (instalación básica). Si consume más de las 4 horas asignadas, las notificaciones push se sustituirán por avisos más sencillos en la propia app. (En el caso de que se desarrolle mediante notificaciones ush hay que tener en cuenta que los usuarios de IPhone no podrán acceder a esa funcionalidad a no ser que tengan la aplicación instalada en la pantalla principal)

   \- **Límite en mapas y distancias:** La integración con OpenRouteService queda fuera del MVP. Si se aborda en una futura iteración, se limitará la prueba inicial a 2 horas y, si resulta compleja, se utilizará Haversine para estimar la cercanía.

   \- **Base de datos básica:** Se han eliminado del alcance inicial las consultas complejas y estadísticas avanzadas dado que nos limitaremos a leer, crear, modificar y borrar datos.

   \- **Plantillas de código:** En lugar de que todo el equipo aprenda React y Node desde cero, nos basaremos en copiar y adaptar la estructura inicial que monte el compañero con más experiencia.  

- Gracias a estos recortes de complejidad, se prioriza la implementación y prueba del recorrido crítico del MVP: gestionar una baja, asignar un trabajador disponible y comprobar que acepta la sustitución. El fichaje y el resumen familiar quedan para iteraciones posteriores.

---

## 10. Riesgos técnicos

### 10.1. Listado de riesgos

A continuación, se identifican los principales riesgos que podrían afectar al desarrollo, rendimiento o adopción del sistema:

1. **Problemas de conectividad:** una pérdida de conexión podría interrumpir la consulta o aceptación de una sustitución.
2. **Dependencia de terceros (API):** una futura integración con OpenRouteService podría fallar o alcanzar su límite de uso. No es una dependencia del MVP.
3. **Errores en la asignación de sustituciones:** los datos de disponibilidad podrían estar desactualizados o el estado de la propuesta podría no reflejar correctamente la aceptación del trabajador.
4. **Curva de aprendizaje:** la falta de experiencia del equipo en React, Node.js/Express y Mongoose podría retrasar la implementación e integración del MVP.
5. **Adopción por parte del usuario:** la interfaz podría resultar poco clara para personas con menor destreza digital.
6. **Desviación de plazos (scope creep):** ampliar los requisitos durante el desarrollo podría impedir terminar el recorrido principal dentro del plazo previsto.

### 10.2. Estrategias de mitigación

Para cada riesgo identificado, se aplicarán las siguientes medidas preventivas antes de que ocurra:

| Riesgo | Estrategia de mitigación |
|---|---|
| **Problemas de conectividad** | Mostrar un aviso claro si falla la consulta o el envío de la respuesta y ofrecer un reintento. No se implementará una cola offline compleja en el MVP. |
| **Dependencia de APIs de mapas** | No integrar OpenRouteService en el recorrido principal del MVP. Antes de desarrollarlo en una iteración posterior, comprobar el límite del endpoint elegido y preparar Haversine como alternativa para estimar distancias. |
| **Errores en la asignación de sustituciones** | Validar de nuevo la disponibilidad del trabajador al confirmar la asignación y actualizar el estado de la solicitud de forma consistente. Probar candidatos disponibles, no disponibles, con conflicto horario y con una propuesta aceptada. |
| **Curva de aprendizaje** | Limitar el tiempo de investigación por tecnología, preparar ejemplos pequeños antes de integrarlos y trabajar por parejas en las partes que el equipo desconozca. Revisar semanalmente si el plan de aprendizaje encaja con las horas disponibles. |
| **Adopción por parte del usuario** | Diseñar una interfaz clara, con textos comprensibles y botones visibles, y probar el recorrido con personas que no hayan participado en su diseño. |
| **Desviación de plazos** | Mantener el alcance del MVP cerrado y terminar el recorrido de sustitución antes de incorporar requisitos opcionales. Revisar el avance en iteraciones cortas y aplazar nuevas peticiones hasta una fase posterior. |
