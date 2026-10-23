# Fase 2 · Viabilidad técnica · Estudio

## Introducción

CUIDALIA plantea como MVP un recorrido principal: que la persona coordinadora localice un servicio afectado por una baja, consulte los trabajadores disponibles, asigne un sustituto y compruebe que este acepta el turno. Para desarrollarlo, se propone utilizar React en el frontend, Node.js y Express en el backend y MongoDB como base de datos, con despliegue inicial en servicios cloud con planes gratuitos. El proyecto es viable si se mantiene este alcance, se trabaja con datos de prueba y se priorizan las funciones indispensables. El principal riesgo es la curva de aprendizaje del equipo y la posibilidad de ampliar el alcance antes de terminar e integrar el recorrido de sustitución.

## 1. Requisitos funcionales

La siguiente tabla reúne los requisitos funcionales de CUIDALIA y su prioridad. Las funciones marcadas como *Should* y *Could* se consideran ampliaciones y no condicionan la finalización del MVP. Las funciones *Won't* quedan expresamente fuera de esta versión.

| ID | Requisito funcional | MoSCoW |
|---|---|---|
| RF-01 | El coordinador o trabajador puede iniciar sesión y acceder únicamente a las opciones permitidas para su rol. | Must |
| RF-02 | El coordinador puede consultar los turnos programados en una vista de cuadrantes. | Must |
| RF-03 | El coordinador puede filtrar los turnos para identificar los servicios afectados por una baja. | Must |
| RF-04 | El sistema muestra trabajadores candidatos y excluye a quienes no están disponibles o tienen un conflicto horario registrado. | Must |
| RF-05 | El coordinador puede asignar un candidato válido a un servicio afectado, el trabajador puede aceptar la propuesta y el sistema actualiza el estado de la sustitución. | Must |
| RF-06 | El coordinador puede crear y modificar manualmente los datos básicos de los turnos desde la interfaz. | Should |
| RF-07 | El trabajador puede registrar la hora de entrada y salida de un servicio asignado. | Should |
| RF-08 | El trabajador puede consultar una lista de tareas del servicio y marcar las que ha completado. | Should |
| RF-09 | El familiar autorizado puede consultar un resumen del servicio basado en las tareas registradas. | Should |
| RF-10 | Los usuarios pueden recibir notificaciones sobre cambios de turno o sustituciones, si se confirma la viabilidad en los dispositivos objetivo. | Could |
| RF-11 | El sistema puede generar un resumen contextual de la visita anterior con tareas pendientes, incidencias abiertas, rutinas y observaciones relevantes para el siguiente profesional (*CUIDALIA Continuidad*). | Could |
| RF-12 | El sistema puede detectar repeticiones en tareas pendientes o incidencias mediante reglas configurables y mostrar los registros que justifican cada aviso. | Could |
| RF-13 | El coordinador puede comparar profesionales mediante criterios de compatibilidad explicables y, si resulta viable, estimaciones de distancia o tiempo de desplazamiento. | Could |
| RF-14 | El sistema puede registrar el grado de ayuda prestada en actividades cotidianas para reflejar la participación de la persona atendida (*CUIDALIA Autonomía*). | Could |
| RF-15 | Coordinación, profesionales y familiares autorizados pueden intercambiar mensajes mediante un chat interno. | Could |
| RF-16 | Los familiares pueden enviar solicitudes de cambios o tareas adicionales y consultar su estado. | Could |
| RF-17 | El trabajador puede activar un acceso SOS para facilitar el aviso a coordinación y consultar teléfonos de emergencia, sin sustituir a los servicios de emergencia. | Could |
| RF-18 | El sistema puede generar un informe mensual de las horas registradas y de las sustituciones para su revisión administrativa. | Could |
| RF-19 | El sistema genera automáticamente cuadrantes mensuales mediante inteligencia artificial o un algoritmo complejo de planificación. | Won't |
| RF-20 | El sistema gestiona pagos o facturación económica, se integra con historiales clínicos de la sanidad pública o incorpora videollamadas. | Won't |

### El MVP

#### Recorrido 1. Gestionar una baja y completar una sustitución

**Objetivo:** permitir que la persona coordinadora cubra un servicio afectado por la baja de un trabajador y compruebe que el sustituto seleccionado ha aceptado el turno.

1. La persona coordinadora inicia sesión y accede a la vista de **Cuadrantes**.
2. Consulta los turnos programados y filtra los servicios afectados por la baja.
3. Selecciona el servicio que necesita cobertura.
4. Consulta la lista de trabajadores candidatos disponibles.
5. El sistema excluye a los trabajadores no disponibles o con conflictos de horario, según los datos de prueba registrados.
6. La persona coordinadora selecciona un candidato y confirma la asignación de la sustitución.
7. El trabajador accede a su interfaz, consulta la sustitución pendiente y la acepta.
8. El sistema actualiza el estado de la sustitución y muestra la confirmación a la persona coordinadora.

**Regla de asignación del MVP:** la persona coordinadora elige directamente a un trabajador de la lista de candidatos válidos. No se enviarán avisos simultáneos a varios trabajadores ni se asignará automáticamente el servicio a la primera persona que lo acepte.

#### Requisitos del MVP

El recorrido se implementará con los cinco requisitos *Must*:

- **RF-01:** autenticación y acceso según el rol.
- **RF-02:** consulta de turnos programados.
- **RF-03:** filtrado de servicios afectados por una baja.
- **RF-04:** consulta de candidatos con validación básica de disponibilidad y conflictos horarios.
- **RF-05:** asignación de la sustitución, aceptación por el trabajador y actualización del estado.

**Queda fuera del núcleo del MVP:** fichaje de entrada y salida, checklist de tareas, resumen funcional para familiares, notificaciones push, monitorización en tiempo real, chat interno, solicitudes familiares, botón SOS, optimización avanzada de rutas, puntuación ponderada de compatibilidad, detección de patrones e informes de horas. El trabajador solo necesita consultar y aceptar la sustitución. El familiar no tiene un recorrido funcional obligatorio en esta primera versión.

**Criterios de aceptación:**

1. Un usuario puede iniciar sesión y solo acceder a las opciones correspondientes a su rol.
2. Coordinación puede localizar un servicio afectado por una baja en la vista de cuadrantes.
3. El sistema no permite seleccionar como candidato válido a un trabajador no disponible o con conflicto horario.
4. Coordinación puede asignar un trabajador válido al servicio afectado.
5. El trabajador puede aceptar la sustitución y el estado actualizado queda visible para coordinación.

La usabilidad se comprobará mediante cinco escenarios cronometrados. El objetivo es completar la identificación y asignación de un candidato válido en un máximo de tres minutos y seis acciones principales de interfaz en, al menos, cuatro de los cinco escenarios. La aceptación del trabajador deberá completarse en menos de un minuto en, al menos, cuatro de cinco pruebas. Estos valores son objetivos de evaluación, no resultados ya obtenidos.

## 2. Requisitos técnicos

### Frontend

Se utilizará **React** para construir la interfaz. La selección de bibliotecas se ajustará a las necesidades del MVP, así como las herramientas destinadas a funciones futuras no deben retrasar el recorrido de sustitución.

| Biblioteca o herramienta | Para qué | Por qué esta |
|---|---|---|
| **React Router** | Navegar entre las vistas y proteger visualmente las rutas según el rol. | Permite organizar las pantallas de la aplicación sin recargar toda la página. La autorización real también debe validarse en el backend. |
| **Tailwind CSS** | Crear y mantener los estilos de la interfaz. | Facilita construir componentes coherentes y adaptar las vistas a diferentes tamaños de pantalla. |
| **Vite** | Ejecutar el servidor de desarrollo y preparar la compilación del frontend. | Ofrece un flujo de desarrollo rápido y una configuración inicial sencilla. |
| **TanStack Query** | Gestionar las peticiones al servidor, estados de carga, errores y caché. | Ayuda a organizar la obtención y actualización de los datos de la API. |
| **Axios** | Realizar peticiones HTTP a la API y centralizar el tratamiento de respuestas y errores. | Permite configurar una instancia común y tratar respuestas como 401 o 403 de forma consistente. |
| **React Hook Form + Zod** | Gestionar y validar los formularios del frontend. | Facilita mostrar errores comprensibles y validar los datos antes de enviarlos. La validación también debe repetirse en el backend. |
| **date-fns** | Formatear fechas y horas y realizar operaciones sencillas con ellas. | Resulta útil para mostrar correctamente los horarios de los servicios. |
| **Lucide React** | Incorporar iconos a la interfaz. | Ofrece iconos consistentes para acompañar botones y acciones. |
| **vite-plugin-pwa** *(posterior al MVP)* | Configurar la instalación de la web como aplicación y funcionalidades PWA. | Puede valorarse en una iteración posterior, ya que no es necesaria para completar el recorrido principal. |

### Backend

Se utilizarán **Node.js y Express** para crear la API que conecta el frontend con MongoDB. El backend validará las peticiones, comprobará los permisos y aplicará las reglas de disponibilidad y estado de las sustituciones.

| Biblioteca o herramienta | Para qué | Por qué esta |
|---|---|---|
| **Express** | Definir rutas de la API, ejecutar middleware y devolver respuestas. | Es el marco previsto para construir el backend con Node.js. |
| **Mongoose** | Definir modelos, validar documentos y consultar MongoDB. | Permite organizar el acceso a los datos mediante modelos. |
| **dotenv** | Cargar variables de configuración desde el entorno. | Evita incluir claves y credenciales directamente en el código fuente. |
| **cors** | Configurar qué orígenes pueden realizar peticiones al backend. | Permite controlar las solicitudes desde el frontend desplegado. CORS no sustituye a la autenticación ni a la autorización. |
| **helmet** | Añadir encabezados HTTP de seguridad. | Ayuda a aplicar medidas habituales de seguridad web. |
| **express-rate-limit** | Limitar el número de peticiones en rutas sensibles, como el inicio de sesión. | Reduce el riesgo de abuso de determinados endpoints. |
| **Zod** | Validar cuerpos, parámetros y consultas recibidos por la API. | Evita procesar datos con formatos incorrectos y permite devolver errores controlados. |
| **nodemon** | Reiniciar el servidor de desarrollo cuando cambien los archivos. | Agiliza el trabajo en local (no es una dependencia necesaria en producción) |
| **cookie-parser** | Leer las cookies enviadas al servidor. | Será útil para gestionar el refresh token almacenado en una cookie. |
| **jsonwebtoken** | Crear y verificar tokens JWT. | Permite implementar la autenticación prevista. |
| **bcrypt** | Generar y comprobar hashes de contraseñas. | Las contraseñas no se almacenarán en texto claro. |
| **web-push** *(posterior al MVP)* | Enviar notificaciones web mediante el estándar Web Push. | Se reserva para una iteración posterior porque las notificaciones push no forman parte del recorrido principal. |

#### Autenticación y roles

En el MVP se implementarán los roles de **coordinador** y **cuidador**, con permisos diferenciados comprobados mediante middleware en cada ruta protegida. El rol de familiar forma parte del diseño global y se habilitará cuando se desarrolle su interfaz en una iteración posterior.

Se propone utilizar JWT, con un *access token* de duración corta y un *refresh token* guardado en una cookie `httpOnly`. Las contraseñas se almacenarán mediante hashes con bcrypt. La autorización se comprobará en el servidor, no solo ocultando opciones en el frontend. En el despliegue deberán configurarse adecuadamente las cookies y los secretos de la aplicación.

#### Servicios externos

OpenRouteService se reserva para una posible ampliación cuyo objetivo sea estimar tiempos de desplazamiento y ayudar a comparar candidatos por distancia o ruta. Esta integración no es necesaria para completar el MVP, que seleccionará candidatos según la disponibilidad y los conflictos horarios registrados. Si se incorpora posteriormente y el servicio falla o se alcanza su cuota, podrá utilizarse Haversine como estimación de distancia en línea recta entre dos coordenadas. La clave de la API se guardará en el servidor, nunca en el frontend.

| Servicio | Para qué | Límite gratuito |
|---|---|---|
| **OpenRouteService** *(posterior al MVP)* | Calcular opcionalmente distancias o tiempos de viaje para comparar candidatos. | El límite depende del endpoint elegido y debe comprobarse en la documentación vigente antes de integrar el servicio. No es una dependencia del MVP. |

### Base de datos

Se propone **MongoDB**, con Mongoose como ODM. El diseño inicial contempla cinco colecciones: `users`, `assistedPersons`, `visits`, `substitutionRequests` y `notifications`. Para el MVP se utilizarán principalmente usuarios, visitas y solicitudes de sustitución.Asimismo, los datos de familiares, tareas, fichaje y notificaciones se incorporarán solo cuando se implementen esas funciones, trabajando con datos ficticios y no se utilizarán datos personales o sanitarios reales para la demostración.

#### Colecciones: campos principales y relaciones

**`users`**

Almacena las cuentas de la aplicación en una colección común, diferenciadas por `rol`: `coordinador`, `cuidador` o `familiar`. Los campos previstos son:

- `_id`, `nombre`, `email`, `passwordHash`, `rol` y `telefono`.
- `perfilCuidador`, cuando corresponda, con experiencia, formación, capacidad para usar grúa, alergia a mascotas, medio de transporte y, si se necesita en una versión posterior, ubicación.
- `pushTokens[]`, únicamente si se incorpora el sistema de notificaciones push.

La contraseña se guarda como hash, nunca en texto claro. Para el MVP solo deben añadirse los campos imprescindibles para autenticación, roles, disponibilidad y sustituciones.

**`assistedPersons`**

Contiene la ficha de la persona atendida. En el diseño completo se prevén `_id`, nombre, dirección, ubicación, grado de dependencia, movilidad, patologías, alergias, dieta, medicación, mascotas y notas. También incluye `cuidadorTitularId` como referencia a `users` y `familiaresIds[]` como referencias a los familiares autorizados.

Los campos sanitarios y de ubicación detallados no son necesarios para el recorrido inicial de sustitución salvo que se justifiquen expresamente. En cualquier versión, el acceso a esta información deberá limitarse a los roles autorizados.

**`visits`**

Cada documento representa un servicio concreto y contiene la referencia a la persona atendida (`personaId`), el trabajador asignado (`cuidadorId`), `inicioPrevisto`, `finPrevisto` y `estado`. En una versión posterior puede incluir `checkIn`, `checkOut` y una lista de `tareas` con descripción, estado, hora de realización y observaciones.

Estados previstos para el modelo general: `programada`, `en_curso`, `completada` y `cancelada`. El recorrido del MVP necesita, como mínimo, identificar los servicios programados y asociarles la sustitución correspondiente.

**`substitutionRequests`**

Gestiona las bajas y sustituciones. Cada solicitud referencia una visita mediante `visitId` y registra `solicitadaPor`, `motivo`, `estado`, `trabajadorPropuestoId` y, cuando corresponda, `aceptadaPor`. Para el MVP bastan los campos que permiten identificar el servicio afectado, el candidato elegido, la respuesta del trabajador y el estado final. La actualización de la solicitud y de la asignación de la visita debe mantenerse coherente.

Estados iniciales propuestos: `pendiente_aceptacion` y `cubierta`. Se propone un trabajador cada vez, es decir, no se envían avisos simultáneos a varios candidatos.

**`notifications`** *(posterior al MVP)*

Guardará avisos con destinatario (`destinatarioId`), tipo, mensaje, indicador de lectura, fecha de creación y una referencia opcional a una visita (`visitId`). Esta colección no es necesaria para el recorrido del MVP, ya que las notificaciones automáticas están fuera de su alcance.

#### Esquema preliminar

```text
users
  _id, nombre, email, passwordHash, rol, telefono
  perfilCuidador: { experiencia, formacion[], puedeUsarGrua,
                    alergiaMascotas, transporte }
  pushTokens[]  (solo si se incorporan notificaciones push)

assistedPersons
  _id, nombre, direccion, ubicacion: { lat, lng }, dependencia,
  movilidad, patologias[], alergias[], dieta,
  medicacion: [{ nombre, dosis, hora }], mascotas, notas,
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

notifications  (posterior al MVP)
  _id, destinatarioId -> users, tipo, mensaje,
  visitId (opcional), leida, createdAt
```

#### Relaciones e índices

- Una persona atendida puede tener muchas visitas y varios familiares autorizados.
- Cada visita pertenece a una persona atendida y tiene un trabajador asignado en cada momento.
- Una visita puede tener una solicitud de sustitución.
- Cada usuario puede tener muchas notificaciones si se incorpora esa funcionalidad.
- Se crearán índices en `visits` por `cuidadorId + inicioPrevisto` y por `personaId + inicioPrevisto` para facilitar consultas de agenda e historial cuando esas funciones se implementen. También se deberán indexar los campos usados para localizar los servicios por fecha y estado si las pruebas lo justifican.

### Infraestructura

Se propone desplegar el frontend en Vercel, el backend en Render y la base de datos en MongoDB Atlas.
| Parte | Dónde se despliega | Condiciones del plan gratuito |
|---|---|---|
| **Frontend** | Vercel | Permite desplegar desde GitHub y automatizar nuevas versiones. Deben revisarse las condiciones y límites vigentes del plan elegido. |
| **Backend** | Render, como Web Service | La revisión inicial del equipo indica 750 horas mensuales y suspensión tras un periodo sin tráfico, lo que puede provocar que la primera petición tarde más. Estos límites deben verificarse antes del despliegue. No se guardarán archivos en el servidor, ya que el plan gratuito puede no ofrecer disco persistente. |
| **Base de datos** | MongoDB Atlas | Se utilizará un clúster gratuito para los datos de prueba. La capacidad exacta disponible debe comprobarse en las condiciones vigentes del plan. |

No se necesitan servicios cloud adicionales ni notificaciones push para el MVP. Si se incorpora `web-push` en una iteración posterior, habrá que comprobar la compatibilidad de los dispositivos objetivo. No se dependerá de un *ping* periódico como solución garantizada para evitar la suspensión del servicio de backend.

## 3. Capacidades del equipo

### Inventario

| Persona | React | Node + Express | MongoDB | Git |
|---|---|---|---|---|
| **Dani** | Mayor experiencia relativa en la estructura inicial de pantallas. | Necesita reforzar los conceptos necesarios para integrar el MVP. | Necesita reforzar los conceptos necesarios para el proyecto. | Nivel por autoevaluar. |
| **Irene** | Necesita reforzar la construcción de pantallas y su conexión con los datos. | Necesita reforzar la API y la lógica del servidor. | Necesita reforzar modelos y operaciones básicas. | Nivel por autoevaluar. |
| **Alejandro** | Necesita reforzar la construcción de pantallas y su conexión con los datos. | Necesita reforzar la API y la lógica del servidor. | Necesita reforzar modelos y operaciones básicas. | Nivel por autoevaluar. |
| **Pablo** | Necesita reforzar la construcción de pantallas y su conexión con los datos. | Necesita reforzar la API y la lógica del servidor. | Necesita reforzar modelos y operaciones básicas. | Nivel por autoevaluar. |

### Lagunas

El equipo ha identificado estas áreas de aprendizaje. Se separan las competencias necesarias para el MVP de las tecnologías opcionales para posteriores iteraciones.

| Tecnología o tema | Quién lo desconoce o debe reforzarlo | Qué hay que aprender exactamente | Cómo y cuándo se va a aprender | Tiempo estimado |
|---|---|---|---|---:|
| **Formularios seguros (React Hook Form + Zod)** | Irene, Dani, Alejandro y Pablo | Validar los datos introducidos y mostrar errores comprensibles. | Crear una pantalla de prueba durante la primera semana. | 5 h |
| **Control de usuarios y permisos (JWT)** | Irene, Dani, Alejandro y Pablo | Controlar el acceso, verificar roles y proteger los datos para que cada usuario solo vea lo autorizado. | Implementarlo mientras se construye el inicio de sesión en el primer sprint. | 6 h |
| **React y construcción de pantallas** | Irene, Alejandro y Pablo. Dani apoyará la estructura inicial | Construir vistas y conectarlas con los datos. | Preparar una estructura base y adaptarla en la primera semana. | 8 h |
| **Node.js y Express** | Irene, Dani, Alejandro y Pablo | Recibir solicitudes de la interfaz y responder mediante una API segura. | Programar en parejas al montar la base del proyecto en el primer sprint. | 6 h |
| **MongoDB** | Irene, Dani, Alejandro y Pablo | Guardar, buscar y actualizar los datos básicos del recorrido de sustitución. | Diseñar los modelos y realizar una prueba conjunta durante la primera semana. | 5 h |
| **PWA y notificaciones** *(posterior al MVP)* | Irene, Dani, Alejandro y Pablo | Instalar la web como aplicación y valorar el envío de avisos. | Solo se realizará una prueba acotada si el recorrido principal ya está terminado. | 4 h |
| **Cálculo de distancias (OpenRouteService)** *(posterior al MVP)* | Equipo al completo | Integrar un servicio para estimar tiempos de desplazamiento. Haversine puede servir como estimación en línea recta. | Prueba opcional, limitada a dos horas, en una iteración posterior. | 2 h |

**Tiempo estimado de aprendizaje:** 30 horas para las áreas necesarias para el MVP y 6 horas opcionales para PWA y mapas. El total previsto es de **36 horas**, siempre que el equipo respete los límites y no intente aprender todas las tecnologías en profundidad antes de comenzar a construir el recorrido principal.

### ¿Es realista?

El MVP es viable de forma condicionada: el alcance es pequeño y el recorrido se puede demostrar con datos ficticios, pero el equipo necesita repartir tareas, aprender mientras implementa y probar pronto la integración entre frontend, backend y base de datos. Las 30 horas previstas para las áreas principales deben tratarse como una estimación, no como una garantía. Si alguna tarea supera el tiempo asignado, se deberá reducir su alcance o pedir apoyo al compañero con más experiencia antes de añadir nuevas funciones.

Para mantener la viabilidad:

- Se terminará primero el recorrido de sustitución con datos de prueba.
- No se integrará OpenRouteService, PWA ni notificaciones push en el núcleo del MVP.
- Se reutilizará la estructura inicial de pantallas y API y se trabajará en parejas en los conceptos menos conocidos.
- Se mantendrán las operaciones de base de datos limitadas a lo que necesite el recorrido principal.
- Se revisará semanalmente el progreso y se aplazarán los requisitos opcionales si existe riesgo para la entrega.
- Se utilizará Git para trabajar con ramas y revisar los cambios mediante pull requests el nivel práctico del equipo deberá comprobarse al inicio.

## 4. Riesgos técnicos

| Riesgo | Tipo | Mitigación |
|---|---|---|
| **Problemas de conectividad** | Técnico / disponibilidad | Mostrar un aviso claro cuando falle la consulta o el envío de la respuesta y permitir reintentar. No se implementará una cola compleja de operaciones sin conexión en el MVP. |
| **Dependencia de APIs de mapas** | Técnico / servicio externo | OpenRouteService no se integrará en el recorrido principal. Antes de abordarlo más adelante se comprobarán los límites del endpoint y se mantendrá Haversine como alternativa para estimar distancias en línea recta. |
| **Errores en la asignación de sustituciones** | Funcional / integridad de datos | Validar de nuevo la disponibilidad al confirmar la asignación, comprobar que la solicitud y la visita se actualizan de forma coherente y probar candidatos disponibles, no disponibles, con conflicto horario y con propuesta aceptada. |
| **Curva de aprendizaje** | Equipo / planificación | Limitar el tiempo de investigación por tecnología, crear ejemplos pequeños antes de integrarlos, trabajar por parejas y revisar semanalmente si el plan cabe en las horas disponibles. |
| **Permisos inadecuados o exposición de datos** | Seguridad / privacidad | Aplicar autorización en el backend, limitar el acceso por rol, guardar contraseñas como hashes y utilizar únicamente datos ficticios durante el desarrollo y la demostración. No incluir datos sanitarios que no sean necesarios para el MVP. |
| **Dificultades de uso** | Usabilidad / adopción | Diseñar una interfaz clara, con textos comprensibles y botones visibles, y probar el recorrido con personas que no hayan participado en su diseño. |
| **Desviación de plazos** | Gestión / planificación | Mantener cerrado el alcance del MVP y terminar el recorrido de sustitución antes de incorporar requisitos opcionales. Revisar el avance en iteraciones cortas y aplazar nuevas peticiones a fases posteriores. |
| **Limitaciones del alojamiento gratuito** | Infraestructura / disponibilidad | Verificar las condiciones vigentes de Vercel, Render y MongoDB Atlas antes del despliegue. Probar el flujo en el entorno desplegado y documentar posibles demoras de arranque o límites de capacidad. |
