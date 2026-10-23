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
### 2.2. Recorrido principal del MVP
### 2.3. Requisitos técnicos: frontend
### 2.4. Requisitos técnicos: backend y autenticación
### 2.5. API externa y mapas
### 2.6. Base de datos: MongoDB
#### Colecciones principales
#### Relaciones e índices
### 2.7. Infraestructura y servicios
### 2.8. Capacidades del equipo y lagunas de conocimiento
### 2.9. Riesgos y medidas de mitigación
## 3. Objetivos y alcance
### 3.1. Objetivo general
### 3.2. Objetivos específicos
### 3.3. Medición del éxito
### 3.4. Plataforma
### 3.5. Usuarios y datos de prueba
### 3.6. Lo que no haremos en esta versión
### 3.7. Hoja de ruta posterior al MVP
# Fase 4 · Recursos · CUIDALIA

## Introducción

El equipo de CUIDALIA está formado por cuatro integrantes, con responsabilidades distribuidas entre el desarrollo frontend, el backend, la base de datos y las pruebas de calidad. Cada integrante tendrá un área principal de responsabilidad y colaborará con el resto del equipo para garantizar la integración de los módulos y el cumplimiento de los requisitos del MVP.

Para desarrollar y gestionar el proyecto se utilizarán herramientas como Visual Studio Code, Node.js, Git y GitHub, junto con herramientas de análisis estático, pruebas y comunicación. La organización del trabajo se apoyará en un tablero de tareas, un flujo de revisión de código mediante Pull Requests y acuerdos de equipo documentados.

## 1. Las personas

### Roles técnicos

| Persona | Rol | De qué responde |
|---|---|---|
| **Daniel Espinosa** | Frontend | Estructura del cliente React, componentes, diseño responsive, navegación protegida por rol e integración con la API. |
| **Irene Foncubierta** | Backend | Servidor Node.js/Express, lógica de negocio, autenticación JWT, middleware de seguridad e integración con servicios externos si se incorporan. |
| **Pablo Reyes** | Base de datos | Modelos y validaciones de Mongoose, colecciones y relaciones de MongoDB Atlas y generación de datos ficticios para las pruebas. |
| **Alejandro Espinosa** | QA y pruebas | Diseño y ejecución de pruebas unitarias y de integración, validación de los recorridos del MVP y revisión de estándares de código. |

Los roles definen la responsabilidad principal de cada integrante, pero no implican que el trabajo se realice de forma aislada. Los cambios deberán revisarse con la persona responsable de la capa correspondiente, y todo el equipo colaborará para resolver bloqueos y problemas de integración.

### Responsables por módulo

| Módulo | Requisitos (RF) | Responsable | Apoyo |
|---|---|---|---|
| Autenticación y accesos | Login, sesiones y permisos por rol. | Daniel Espinosa | Irene Foncubierta |
| Cuadrantes y sustituciones | Consulta de turnos, filtro de baja, validación de disponibilidad, asignación y aceptación. | Irene Foncubierta | Alejandro Espinosa |
| Modelos y persistencia | Modelos de usuarios, visitas y solicitudes de sustitución; datos de prueba e índices. | Pablo Reyes | Irene Foncubierta |
| Calidad del MVP | Pruebas de restricciones horarias, estado de sustitución y recorrido completo. | Alejandro Espinosa | Daniel Espinosa |

La asignación de responsables podrá ajustarse si la carga real de trabajo resulta desigual. El responsable de cada módulo coordinará las tareas, revisará los cambios y mantendrá la coherencia de su área, sin necesidad de implementar personalmente todas las modificaciones.

### Comunicación

Ver [Contrato de equipo](../CONTRATO.md). Discord será el canal principal para la coordinación, las reuniones y la resolución de dudas; GitHub se utilizará para registrar las tareas y las decisiones técnicas, y WhatsApp quedará como canal complementario para avisos rápidos. Los bloqueos se comunicarán indicando el contexto, los intentos realizados y la ayuda necesaria.

## 2. La tecnología

### Stack, servicios y APIs

Ver [Fase 2 · Requisitos técnicos](02-viabilidad-tecnica.md#2-requisitos-técnicos).

El proyecto utilizará React para el frontend, Node.js y Express para el backend, MongoDB Atlas como base de datos y Mongoose para definir los modelos y sus validaciones. La autenticación se implementará mediante JWT y la comunicación entre el cliente y el servidor se realizará a través de una API. La incorporación de servicios externos dependerá de las necesidades y prioridades del proyecto.

### Herramientas de desarrollo

| Para qué | Herramienta |
|---|---|
| Editor y estilo | Visual Studio Code, ESLint y Prettier. |
| Versión de Node | Node.js LTS, con la misma versión fijada para todos los integrantes. |
| Probar la API | Postman o Thunder Client. |
| Tests | Vitest, si se utiliza Vite en el frontend; Jest y Supertest para las pruebas del backend. |
| Control de versiones y revisión | Git y GitHub. |
| Gestión de tareas | GitHub Issues y GitHub Projects. |

Estas herramientas permitirán mantener un entorno de desarrollo común, detectar errores habituales, comprobar los endpoints antes de integrarlos en la interfaz y verificar el comportamiento del MVP mediante pruebas unitarias y de integración.

## 3. La gestión

### Tablero

El trabajo se organizará mediante el [GitHub Projects de CUIDALIA](https://github.com/ifonlob/Cuidalia/projects). El tablero tendrá las columnas `Backlog`, `Todo`, `In Progress`, `In Review` y `Done`, que permitirán visualizar el estado de las tareas desde su planificación hasta su finalización.

Cada tarea estará vinculada a una issue de GitHub e incluirá una persona responsable y un criterio de finalización. El equipo revisará semanalmente el estado del tablero y el cumplimiento de los hitos, identificando bloqueos y reajustando prioridades cuando sea necesario.

### Ramas

El proyecto seguirá un flujo de trabajo basado en ramas y revisión de código:

- **`main`:** contendrá las versiones estables destinadas a las entregas.
- **`develop`:** será la rama de integración del trabajo del equipo.
- **`feature/*`:** se utilizará para desarrollar nuevas funcionalidades a partir de `develop`. También podrán emplearse prefijos específicos, como `feat/` para funcionalidades y `docs/` para documentación.

Se utilizará el siguiente flujo de trabajo:

`Issue → rama de tarea → commits → Pull Request → review aprobada por otro integrante → merge`

Las normas de trabajo con Git serán las siguientes:

- No se realizarán pushes directos a `main` ni a `develop`.
- Las ramas de tarea se crearán a partir de `develop` y tendrán nombres descriptivos, como `feat/23-asignar-sustitucion` o `docs/24-propuesta-final`.
- Cada Pull Request deberá vincularse a su issue correspondiente mediante `Closes #N`, cuando proceda.
- Al menos otro integrante deberá revisar y aprobar los cambios antes del merge. Nadie aprobará ni fusionará su propio Pull Request.
- Al cerrar un hito o sprint, se abrirá un Pull Request desde `develop` hacia `main` para incorporar la versión estable.

Este procedimiento facilitará la revisión de los cambios, reducirá los conflictos de integración y permitirá mantener un historial de desarrollo trazable.

### Estructura de carpetas

El repositorio tendrá una estructura organizada por responsabilidades:

```text
Cuidalia/
├── client/       # Aplicación frontend
├── server/       # Servidor backend y API
├── docs/         # Documentación del proyecto
├── .gitignore    # Archivos excluidos del repositorio
└── README.md     # Información general del proyecto
```

El directorio `client/` contendrá el código de la aplicación React, mientras que `server/` incluirá el servidor Node.js/Express y la lógica de negocio. La documentación del proyecto se mantendrá dentro de `docs/`.

El archivo `.gitignore` excluirá, como mínimo, `node_modules/`, `.env` y los archivos temporales. No se almacenarán contraseñas, tokens ni claves de API en el repositorio.

### Organización de las tareas y control del alcance

Además de los riesgos técnicos, la coordinación del equipo será fundamental para cumplir con la entrega. Para controlar el alcance y mantener el avance del proyecto:

- Se revisará semanalmente el estado del tablero y el cumplimiento de los hitos.
- Las tareas se dividirán en cambios pequeños que puedan revisarse mediante Pull Requests.
- Si una funcionalidad supera la estimación prevista, se estudiará primero si puede simplificarse o aplazarse.
- Las funcionalidades clasificadas como *Could* no se iniciarán hasta que los cinco requisitos *Must* estén integrados y probados.
- La incorporación de nuevas funcionalidades requerirá una decisión conjunta y una actualización explícita de las prioridades y del alcance.

Estas medidas permitirán priorizar los requisitos esenciales del MVP, anticipar posibles retrasos y distribuir el trabajo de forma equilibrada.
## 5. Conclusión
## Referencias técnicas principales
