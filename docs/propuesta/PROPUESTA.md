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
## 4. Recursos y organización del equipo
### 4.1. Personas y roles técnicos   

| Integrante | Rol técnico | Responsabilidades principales |
|---|---|---|
| **Daniel Espinosa** | Frontend | Estructura del cliente React, componentes, diseño responsive, navegación protegida por rol e integración con la API. |
| **Irene Foncubierta** | Backend | Servidor Node.js/Express, lógica de negocio, autenticación JWT, middleware de seguridad e integración con servicios externos si se incorporan. |
| **Pablo Reyes** | Base de datos | Modelos y validaciones de Mongoose, colecciones y relaciones de MongoDB Atlas y generación de datos ficticios para las pruebas. |
| **Alejandro Espinosa** | QA y pruebas | Diseño y ejecución de pruebas unitarias y de integración, validación de los recorridos del MVP y revisión de estándares de código. |

Los roles distribuyen la responsabilidad principal, pero no convierten cada área en trabajo aislado. Los cambios deben revisarse con la persona responsable de la capa correspondiente y el equipo colaborará para resolver bloqueos e integración.

### 4.2. Responsables por módulo   


| Módulo | Alcance | Responsable | Apoyo |
|---|---|---|---|
| Autenticación y accesos | Login, sesiones y permisos por rol. | Daniel Espinosa | Irene Foncubierta |
| Cuadrantes y sustituciones | Consulta de turnos, filtro de baja, validación de disponibilidad, asignación y aceptación. | Irene Foncubierta | Alejandro Espinosa |
| Modelos y persistencia | Modelos de usuarios, visitas y solicitudes de sustitución; datos de prueba e índices. | Pablo Reyes | Irene Foncubierta |
| Calidad del MVP | Pruebas de restricciones horarias, estado de sustitución y recorrido completo. | Alejandro Espinosa | Daniel Espinosa |

La distribución se ajustará si la carga real de cada módulo resulta desigual. El responsable no implementará necesariamente todos los cambios; se encargará de coordinar, revisar y mantener coherencia en su área.


### 4.3. Herramientas de desarrollo   

| Uso | Herramienta | Motivo |
|---|---|---|
| Editor | Visual Studio Code | Entorno común de desarrollo. |
| Entorno de ejecución | Node.js LTS, con la misma versión fijada para todos | Evitar diferencias de compatibilidad. |
| Estilo y formato | ESLint y Prettier | Mantener un formato coherente y detectar errores habituales. |
| Pruebas de API | Postman o Thunder Client | Comprobar endpoints antes de conectarlos a la interfaz. |
| Pruebas frontend | Vitest, si se utiliza con Vite | Comprobar el comportamiento de componentes y funciones. |
| Pruebas backend | Jest y Supertest | Validar rutas y respuestas HTTP. |
| Repositorio y gestión | Git, GitHub Issues y GitHub Projects | Control de versiones, tareas, revisión y trazabilidad. |

### 4.4. Gestión del trabajo y flujo de Git   

El proyecto se gestionará desde [GitHub Projects de CUIDALIA](https://github.com/ifonlob/Cuidalia/projects). El tablero incluirá las columnas `Backlog`, `Todo`, `In Progress`, `In Review` y `Done`. Cada tarea se vinculará a una issue con persona responsable y criterio de finalización.

El flujo establecido será:

`Issue → rama de tarea → commits → Pull Request → review aprobada por otro integrante → merge`.

- `main` contendrá las versiones estables destinadas a entregas.
- `develop` será la rama de integración del trabajo.
- Las ramas de tarea se crearán a partir de `develop`, con nombres descriptivos como `feat/23-asignar-sustitucion` o `docs/24-propuesta-final`.
- No se harán pushes directos a `main` ni a `develop`.
- Cada Pull Request deberá vincularse con su issue, utilizando `Closes #N` cuando corresponda.
- Al menos otro compañero revisará y aprobará los cambios antes del merge. Nadie aprobará ni fusionará su propio PR.
- Al cerrar un hito o sprint, se abrirá un PR de `develop` hacia `main`.

El repositorio mantendrá la documentación del proyecto dentro de `docs/`, el frontend en `client/` y el backend en `server/`. El archivo `.gitignore` excluirá, como mínimo, `node_modules/`, `.env` y archivos temporales. No se almacenarán contraseñas, tokens ni claves API en el repositorio.


### 4.5. Comunicación y acuerdos    

El equipo utilizará Discord como canal principal de coordinación, reuniones y resolución de dudas, y GitHub para registrar el trabajo técnico y las decisiones vinculadas a issues o Pull Requests. WhatsApp podrá utilizarse como canal complementario para avisos rápidos, sin sustituir la documentación de decisiones relevantes en el repositorio.

Las normas de convivencia, la frecuencia de las reuniones, los compromisos de trabajo y la resolución de conflictos quedan recogidos en [`docs/CONTRATO.md`](CONTRATO.md). Cualquier bloqueo que impida avanzar se comunicará al equipo con el contexto, lo que se ha intentado y la ayuda necesaria.

### 4.6. Riesgos organizativos y control de alcance    

Además de los riesgos técnicos, la coordinación del equipo es fundamental para llegar a la entrega. Para ello:

- Se revisará semanalmente el estado del tablero y el cumplimiento de los hitos.
- Las tareas se dividirán en cambios pequeños que puedan revisarse mediante un PR.
- Si una función supera la estimación prevista, primero se revisará si puede simplificarse o aplazarse.
- Las funciones *Could* no se iniciarán hasta que los cinco requisitos *Must* estén integrados y probados.
- La introducción de nuevas funcionalidades requerirá una decisión conjunta y una actualización explícita de la prioridad y del alcance.

## 5. Conclusión

CUIDALIA responde a un problema operativo concreto de los servicios de ayuda a domicilio: coordinar cambios y sustituciones sin perder la información necesaria para prestar el servicio. La investigación inicial y las reseñas revisadas justifican continuar explorando la idea, pero la frecuencia e impacto de los problemas deberán validarse con profesionales del sector.

La primera versión se centrará en un recorrido completo y demostrable: detectar un servicio afectado por una baja, localizar un trabajador disponible, asignar la sustitución y confirmar su aceptación. El resto de las funcionalidades se priorizará de manera gradual para evitar que el proyecto se convierta en una plataforma demasiado ambiciosa para el tiempo del módulo.

La propuesta de diferenciación de CUIDALIA se basa en conectar la información de las visitas con el contexto que necesita el profesional siguiente, facilitar la revisión de patrones repetidos y mostrar criterios comprensibles para apoyar las decisiones de coordinación. CUIDALIA Autonomía se plantea como una evolución futura centrada en la persona atendida. Estas capacidades deberán ser contrastadas mediante entrevistas y pruebas de prototipo, y no se presentan como exclusivas de las soluciones existentes.

El uso del stack MERN, el empleo de datos ficticios, la autenticación por roles, los riesgos identificados y el reparto de responsabilidades proporcionan una base inicial para desarrollar el proyecto. La viabilidad final dependerá de mantener el alcance cerrado, priorizar el aprendizaje de las tecnologías esenciales y revisar mediante pruebas cada parte del recorrido principal.

**CUIDALIA pretende pasar de registrar lo que ocurre en cada visita a convertir esa información en contexto útil para las decisiones que ayudan a mantener la continuidad de la atención, siempre con supervisión humana y respeto por la privacidad de las personas.**


## Referencias técnicas principales

- [Documentación de GESAD Mobile](https://play.google.com/store/apps/details?id=gt.grupotrevenque.gesadmobile)
- [CIBERSAD](https://cigesoc.es/cibersad/)
- [ecoSoftWEB](https://ecosoftconsulting.net/programas-para-empresas-de-ayuda-a-domicilio/)
- [OpenRouteService: restricciones de la API](https://staging.openrouteservice.org/restrictions/)
- [OpenRouteService: migración del endpoint API](https://ask.openrouteservice.org/t/reducing-the-quota-of-deprecated-api-api-openrouteservice-org/8013)
- [Vercel Hobby](https://vercel.com/docs/plans/hobby)
- [Render: límites del plan gratuito](https://render.com/docs/free)
- [MongoDB Atlas: límites del clúster gratuito](https://www.mongodb.com/docs/atlas/reference/free-shared-limitations/)
- [Apple: Web Push en aplicaciones web](https://developer.apple.com/documentation/usernotifications/sending-web-push-notifications-in-web-apps-and-browsers)
- [Reglamento General de Protección de Datos (RGPD)](https://eur-lex.europa.eu/eli/reg/2016/679/oj?locale=es)

