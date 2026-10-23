# CUIDALIA — Propuesta de proyecto grupal
## Introducción
## 1. El problema y las personas destinatarias
### 1.1. Identificación de la necesidad
### 1.2. Personas afectadas e impacto
### 1.3. Evidencias iniciales
### 1.4. Personas usuarias
#### Persona 1. Coordinador o coordinadora
#### Persona 2. Profesional de atención directa
#### Persona 3. Familiar autorizado
#### La persona atendida como centro del servicio
### 1.5. Análisis de la competencia
#### GESAD Mobile
#### CIBERSAD
#### ecoSoftWEB
#### Conclusión del análisis competitivo
### 1.6. Propuesta de valor diferencial
## 2. Viabilidad técnica

### 2.1. Requisitos funcionales y priorización MoSCoW

Los requisitos se expresan mediante acciones concretas y se priorizan para mantener el alcance controlado. El MVP tendrá cinco requisitos *Must*, menos de la mitad de los veinte requisitos recogidos.

| ID | Prioridad | Requisito funcional |
|---|---|---|
| RF-01 | **Must** | Autenticar a cada usuario y mostrar las opciones permitidas según su rol. |
| RF-02 | **Must** | Consultar los turnos programados en una vista de cuadrantes. |
| RF-03 | **Must** | Filtrar los turnos para identificar los servicios afectados por una baja. |
| RF-04 | **Must** | Mostrar candidatos a sustitución y descartar a quienes no estén disponibles o tengan un conflicto horario. |
| RF-05 | **Must** | Asignar un candidato a la visita afectada y permitir que ese trabajador acepte la sustitución desde su interfaz. |
| RF-06 | **Should** | Crear y modificar manualmente los datos básicos de un turno desde la interfaz de coordinación. |
| RF-07 | **Should** | Registrar la entrada y salida del trabajador en un servicio asignado. |
| RF-08 | **Should** | Marcar como completadas las tareas previstas para una visita y guardar el resultado. |
| RF-09 | **Should** | Mostrar al familiar autorizado un resumen de las tareas registradas en el servicio. |
| RF-10 | **Could** | Enviar notificaciones push de cambios relevantes, si se confirma su viabilidad técnica en los dispositivos objetivo. |
| RF-11 | **Could** | Generar un resumen contextual de la visita anterior con tareas pendientes, incidencias abiertas y rutinas relevantes para el siguiente profesional. |
| RF-12 | **Could** | Señalar patrones repetidos mediante reglas configurables y mostrar los registros que justifican cada aviso. |
| RF-13 | **Could** | Comparar candidatos según criterios explicables de compatibilidad y, si resulta viable, calcular distancias o tiempos de desplazamiento con una API externa. |
| RF-14 | **Could** | Registrar el grado de ayuda prestada en determinadas actividades cotidianas para reflejar la participación de la persona atendida. |
| RF-15 | **Could** | Incorporar herramientas complementarias de comunicación, como chat interno y solicitudes familiares, con seguimiento de su estado. |
| RF-16 | **Could** | Añadir un botón SOS informativo que facilite avisar a coordinación y acceder a los teléfonos de emergencia, sin sustituir los servicios de emergencia. |
| RF-17 | **Could** | Generar un informe mensual de horas registradas y sustituciones, con opción de exportación para revisión administrativa. |
| RF-18 | **Won't** | Generar automáticamente cuadrantes mensuales mediante inteligencia artificial o un algoritmo complejo de planificación. |
| RF-19 | **Won't** | Gestionar pagos, cobros bancarios o facturación económica dentro de la aplicación. |
| RF-20 | **Won't** | Integrarse con historiales clínicos de la sanidad pública ni incorporar videollamadas. |

Los requisitos RF-01 a RF-05 forman el recorrido principal del MVP. Los restantes no se incorporarán al núcleo obligatorio. Si el equipo dispone de tiempo adicional, se abordarán según la prioridad de la hoja de ruta y solo tras completar y probar el recorrido principal.

### 2.2. Recorrido principal del MVP

**Objetivo del recorrido:** permitir que coordinación cubra un servicio afectado por una baja y que el trabajador seleccionado confirme la aceptación.

1. La persona coordinadora inicia sesión.
2. Abre la sección **Cuadrantes** y consulta los servicios programados.
3. Filtra los turnos para localizar la visita afectada por la baja.
4. Selecciona la visita y consulta los trabajadores candidatos disponibles.
5. El sistema excluye candidatos con incompatibilidades de horario o que no cumplan requisitos obligatorios configurados.
6. La persona coordinadora elige a un trabajador y confirma la asignación.
7. El trabajador entra en su interfaz, consulta la sustitución pendiente y la acepta.
8. CUIDALIA actualiza el estado de la visita y muestra la confirmación a coordinación.

**Decisión de alcance:** para evitar la contradicción detectada en la revisión técnica, en el MVP la persona coordinadora elegirá y asignará directamente a un trabajador disponible. No se implementará en esta versión un sistema de difusión simultánea a varios trabajadores donde el primero que acepte se quede con el servicio.

No se exige que el MVP incorpore geolocalización avanzada, sincronización offline, notificaciones push, chat, detección de patrones o puntuación ponderada de compatibilidad. Esas funciones podrán estudiarse como ampliaciones. Los recorridos de fichaje y checklist del trabajador y el resumen del familiar se mantienen como prioridades posteriores, no como recorridos imprescindibles de la primera entrega.

### 2.3. Requisitos técnicos: frontend

El frontend se desarrollará con React y se adaptará a pantallas de escritorio y móvil. El objetivo inicial es construir una interfaz web responsive; la instalación como PWA se incorporará solo si no compromete el MVP.

- **React:** permite construir la interfaz a partir de componentes reutilizables y actualizar las vistas según el estado de turnos y sustituciones.
- **React Router:** organizará las rutas de la aplicación y permitirá restringir las vistas según el rol. Las comprobaciones de permisos también se realizarán en el backend; proteger una ruta visualmente no es suficiente.
- **Tailwind CSS:** facilitará la creación y el mantenimiento de estilos responsive con criterios compartidos por el equipo.
- **Axios:** realizará las peticiones HTTP a la API REST y centralizará la configuración de errores y cabeceras.
- **TanStack Query:** se evaluará para administrar la carga, caché y actualización de datos del servidor. Como todo el equipo parte sin experiencia en esta biblioteca, se prescindirá de ella si aumenta innecesariamente el tiempo de aprendizaje del MVP.
- **React Hook Form y Zod:** podrán utilizarse si se necesitan formularios más complejos. La validación del backend será obligatoria independientemente de la validación visual.
- **date-fns y Lucide React:** se incorporarán únicamente si resultan útiles para el formato de horarios y los iconos de la interfaz.
- **Vite:** se utilizará como herramienta de desarrollo y empaquetado de React, no como biblioteca adicional.
- **vite-plugin-pwa:** se deja fuera del núcleo funcional si exige dedicar demasiado tiempo a la instalación, caché o sincronización offline. Una primera versión puede funcionar como web responsive.

La selección final de dependencias se mantendrá reducida y documentada en `package.json` y en el README.

### 2.4. Requisitos técnicos: backend y autenticación

El backend se implementará con Node.js y Express, exponiendo una API REST que gestionará autenticación, usuarios, turnos, disponibilidad y sustituciones.

La autenticación se basará en credenciales y tokens JWT. La propuesta técnica contempla un *access token* de duración corta y un *refresh token* almacenado en una cookie `httpOnly`. Las contraseñas se almacenarán mediante un hash creado con `bcrypt`, nunca en texto plano. Para ello se utilizarán bibliotecas como `jsonwebtoken` y `cookie-parser`.

El backend incluirá middleware de autenticación y autorización por rol, validación de entradas y configuración de seguridad. Se valorará utilizar:

- **Mongoose:** definir esquemas, validar documentos y establecer referencias entre colecciones de MongoDB.
- **Zod:** validar cuerpos, parámetros y consultas recibidos por la API.
- **Helmet:** configurar cabeceras HTTP de seguridad.
- **CORS:** permitir únicamente los orígenes necesarios para el frontend.
- **express-rate-limit:** limitar intentos de acceso y reducir peticiones abusivas.
- **dotenv:** cargar secretos y configuración desde variables de entorno.
- **Jest y Supertest:** realizar pruebas de integración de endpoints y respuestas HTTP.

La gestión de cookies debe configurarse con atributos apropiados para el despliegue, como `Secure`, `HttpOnly` y `SameSite`, junto con medidas frente a solicitudes no autorizadas cuando sean necesarias. La clave de MongoDB, los secretos JWT y cualquier clave de API permanecerán en variables de entorno y no se subirán al repositorio.

### 2.5. API externa y mapas

OpenRouteService no es necesaria para completar el MVP inicial. La integración se aplaza a la fase en la que se implemente la comparación de candidatos por distancia o tiempo de viaje.

Si se incorpora, la clave se utilizará únicamente desde el servidor y se comprobarán los límites del endpoint específico antes de implementar la funcionalidad. El endpoint **Matrix** tiene restricciones y cuotas distintas de Directions; no debe asumirse que el límite de cálculo de rutas es aplicable a las matrices. Se revisará el panel de la cuenta antes de desarrollar esta parte y se utilizará una estimación por Haversine como alternativa para ordenar candidatos por cercanía aproximada.

También se tendrá en cuenta que el servicio ha cambiado su endpoint público: la documentación y el anuncio del proveedor indican la migración desde `api.openrouteservice.org` hacia `api.heigit.org`, con cierre del endpoint antiguo previsto para noviembre de 2026. La integración futura deberá utilizar el endpoint vigente y verificar de nuevo las condiciones antes de la defensa.

Referencias oficiales:
- [Restricciones de OpenRouteService](https://staging.openrouteservice.org/restrictions/)
- [Documentación del servicio Matrix](https://openrouteservice.org/dev/#/api-docs/matrix)
- [Anuncio sobre la migración del endpoint](https://ask.openrouteservice.org/t/reducing-the-quota-of-deprecated-api-api-openrouteservice-org/8013)

### 2.6. Base de datos: MongoDB

Se utilizará MongoDB como base de datos documental y Mongoose para definir modelos y validaciones. El diseño es preliminar y se irá ajustando a medida que se implemente el MVP. Para la primera versión se priorizarán los datos necesarios para usuarios, turnos y sustituciones.

#### Colecciones principales

**`users`** almacena los usuarios de la aplicación y su rol. En los cuidadores incluirá los datos operativos necesarios para consultar disponibilidad y requisitos del servicio.

```text
users
  _id, nombre, email, passwordHash, rol,
  telefono,
  perfilCuidador: {
    formacion[], experiencia,
    puedeUsarGrua,
    alergiaMascotas,
    transporte,
    ubicacion: { lat, lng }
  }
```

**`assistedPersons`** representa a las personas atendidas y contiene solo los datos necesarios para la función correspondiente. Los datos de salud, medicación y dependencia se consideran especialmente sensibles y no se utilizarán datos reales en la demo académica.

```text
assistedPersons
  _id, nombrePrueba, direccionPrueba,
  ubicacion: { lat, lng }, necesidadesServicio[],
  rutinasOperativas[], cuidadorTitularId -> users,
  familiaresIds[] -> users
```

**`visits`** registra los servicios programados y su estado. En el alcance posterior podrá guardar registros de entrada, salida y tareas completadas.

```text
visits
  _id, personaId -> assistedPersons,
  cuidadorId -> users,
  inicioPrevisto, finPrevisto,
  estado: "programada" | "afectada_baja" |
          "sustitucion_pendiente" | "cubierta" |
          "completada" | "cancelada"
```

**`substitutionRequests`** registra el motivo de la sustitución y el resultado de la asignación, de manera que se conserve la trazabilidad de la visita afectada.

```text
substitutionRequests
  _id, visitId -> visits,
  solicitadaPor -> users,
  motivo,
  estado: "abierta" | "asignada" | "aceptada" | "cancelada",
  candidatoId -> users,
  creadaEn, actualizadaEn
```

**`notifications`**, si se implementa la notificación interna, almacenará avisos y su estado de lectura. No se considera necesario desarrollar un sistema de notificaciones push para cerrar el MVP.

```text
notifications
  _id, destinatarioId -> users,
  tipo, mensaje, visitId (opcional),
  leida, createdAt
```

#### Relaciones e índices

Una persona atendida puede tener varios servicios y familiares autorizados. Cada visita se asocia a una persona atendida y a un trabajador. Una visita puede generar una solicitud de sustitución y cada usuario puede recibir avisos.

Se crearán índices en `visits` para las búsquedas frecuentes, especialmente por `cuidadorId + inicioPrevisto` y por `personaId + inicioPrevisto`. Las relaciones familiares deberán limitar la consulta a la información autorizada y el backend verificará los permisos en cada endpoint.

### 2.7. Infraestructura y servicios

- **Frontend:** se propone Vercel para desplegar la aplicación React durante la demostración académica. El plan Hobby es de uso personal/no comercial; por tanto, solo se empleará para el contexto compatible con sus condiciones. Si el uso se convirtiera en comercial, habría que escoger un plan o proveedor adecuado.
- **Backend:** se propone Render para alojar la API Express. El servicio gratuito puede suspenderse tras 15 minutos sin tráfico y tardar alrededor de un minuto en reactivarse. Esta limitación se comunicará durante la demo y no se almacenarán archivos persistentes en el sistema de archivos del servidor.
- **Base de datos:** MongoDB Atlas, con su clúster gratuito. La documentación actual indica un límite de almacenamiento de 0,5 GB, suficiente para un conjunto de datos pequeño y ficticio, siempre que se respeten sus restricciones operativas.
- **Control de versiones:** Git y GitHub para alojar el código, gestionar issues y revisar Pull Requests.

Las condiciones de los planes gratuitos pueden cambiar y deben comprobarse al realizar el despliegue. Referencias oficiales:
- [Vercel Hobby](https://vercel.com/docs/plans/hobby)
- [Render: despliegue gratuito y limitaciones](https://render.com/docs/free)
- [MongoDB Atlas: límites del clúster gratuito](https://www.mongodb.com/docs/atlas/reference/free-shared-limitations/)

Las notificaciones push no formarán parte del núcleo del MVP. Si se estudian en una iteración posterior, se verificará la compatibilidad en los dispositivos previstos. En iOS, Web Push está disponible para web apps añadidas a la pantalla de inicio desde iOS 16.4, por lo que la familia no puede depender exclusivamente de ese mecanismo en la primera versión.

Referencia: [Apple Developer — Web Push en aplicaciones web](https://developer.apple.com/documentation/usernotifications/sending-web-push-notifications-in-web-apps-and-browsers).

### 2.8. Capacidades del equipo y lagunas de conocimiento

La evaluación inicial indica que solo Daniel tiene algo de experiencia previa con React. Según la retroalimentación técnica, el equipo parte sin experiencia práctica suficiente en Express, JWT y TanStack Query. Las demás tecnologías del stack requieren aprendizaje y práctica durante el módulo. Esta situación obliga a limitar la complejidad y no asumir que todas las funciones avanzadas son viables.

| Tecnología o área | Situación inicial del equipo | Medida propuesta |
|---|---|---|
| React y composición de vistas | Daniel cuenta con cierta experiencia; el resto parte de un nivel inicial. | Daniel preparará una estructura base sencilla y se harán ejercicios cortos antes de crear las vistas del MVP. |
| Node.js y Express | Experiencia práctica insuficiente en el equipo. | Construir primero una API mínima con rutas, controladores y middleware; trabajar por parejas en los endpoints principales. |
| MongoDB y Mongoose | Conocimientos iniciales que deben consolidarse. | Diseñar las colecciones imprescindibles antes de implementar consultas complejas. |
| Autenticación JWT y autorización por roles | Sin experiencia práctica suficiente. | Implementar login y una sola ruta protegida primero; probar que un rol no pueda acceder a recursos ajenos. |
| TanStack Query | Sin experiencia previa según la evaluación inicial. | Considerarla opcional. No introducirla si Axios y el estado local bastan para completar el MVP. |
| Formularios y validación | Requiere práctica con React Hook Form/Zod o alternativas. | Probar un formulario pequeño y validar siempre también los datos recibidos por el backend. |
| PWA y notificaciones push | Requiere aprendizaje adicional y depende de compatibilidad del dispositivo. | Aplazarlo después del MVP; si se prueba, fijar un límite de tiempo y una alternativa visible en la aplicación. |
| OpenRouteService y matrices | Requiere práctica con la API y sus cuotas. | Aplazar su integración y limitar la prueba a un experimento corto; usar Haversine o filtros básicos si no compensa. |

La estimación inicial de aprendizaje recogida en la Fase 2 era de unas 36 horas en total: PWA y notificaciones (4 h), formularios y validación (5 h), JWT y permisos (6 h), OpenRouteService (2 h), React (8 h), Node/Express (6 h) y MongoDB (5 h). Esta estimación debe revisarse al cerrar el calendario real del módulo. Para reducir el riesgo, las horas de PWA y OpenRouteService se consideran aplazables, ya que no son necesarias para completar el recorrido principal del MVP.

El equipo no intentará aprender todas las bibliotecas a la vez. Se priorizarán React básico, Express, persistencia con Mongoose y autenticación por roles. Si al comparar horas disponibles y trabajo pendiente la planificación deja de ser realista, se recortarán las funciones *Should* y *Could* antes de añadir complejidad.

### 2.9. Riesgos y medidas de mitigación

| Riesgo | Impacto posible | Mitigación previa |
|---|---|---|
| Curva de aprendizaje de React, Express, Mongoose y JWT. | Retrasos, errores y dificultad para integrar el trabajo. | Crear una prueba técnica mínima al comienzo; trabajar en parejas en las primeras rutas; posponer librerías opcionales y funciones avanzadas. |
| Ampliación del alcance. | El equipo intenta completar demasiados recorridos y deja el principal a medias. | Congelar el MVP en RF-01 a RF-05 y aceptar nuevas funciones solo después de probar el recorrido de baja y sustitución. |
| Errores al asignar sustitutos. | Se asigna un turno a una persona no disponible o con conflicto horario. | Validar en backend la disponibilidad y las restricciones obligatorias y crear pruebas para casos válidos e inválidos. |
| Fallos o agotamiento de cuota de una API externa. | No se pueden obtener distancias o tiempos de desplazamiento. | Excluir la API del MVP; si se incorpora más adelante, comprobar cuotas del endpoint Matrix y disponer de cálculo aproximado por Haversine. |
| Corte de conexión durante el registro. | Un registro podría no llegar al servidor. | No implementar sincronización offline compleja en el MVP. Si una acción posterior admite reintentos, conservar un estado visible de «pendiente de enviar» y permitir reintentar. No usar Redis ni colas distribuidas para unas pocas operaciones de demostración. |
| Limitaciones del hosting gratuito. | El backend puede tardar en responder tras un periodo de inactividad o alcanzar límites del plan. | Probar el despliegue antes de la defensa, documentar el tiempo de reactivación de Render y disponer de una demo local como alternativa. |
| Acceso indebido a información sensible. | Un usuario puede consultar información de otra persona. | Usar datos ficticios, validar roles en el servidor, limitar las consultas por usuario y revisar los permisos mediante pruebas. No almacenar secretos en Git. |
| Dificultad de uso para personas con menor destreza digital. | Se cometen errores o se abandona el proceso. | Utilizar etiquetas claras, pocos pasos, botones reconocibles y mensajes de confirmación; realizar pruebas con personas ajenas al diseño. |
| Notificaciones no disponibles en todos los dispositivos. | El trabajador no ve a tiempo un aviso push. | No depender de push para el recorrido crítico; mostrar la sustitución pendiente dentro de la aplicación y comunicar las limitaciones de PWA/iOS. |
## 3. Objetivos y alcance
### 3.1. Objetivo general
### 3.2. Objetivos específicos
### 3.3. Medición del éxito
### 3.4. Plataforma
### 3.5. Usuarios y datos de prueba
### 3.6. Lo que no haremos en esta versión
### 3.7. Hoja de ruta posterior al MVP
## 4. Recursos y organización del equipo
### 4.1. Personas y roles técnicos
### 4.2. Responsables por módulo
### 4.3. Herramientas de desarrollo
### 4.4. Gestión del trabajo y flujo de Git
### 4.5. Comunicación y acuerdos
### 4.6. Riesgos organizativos y control de alcance
## 5. Conclusión
## Referencias técnicas principales
