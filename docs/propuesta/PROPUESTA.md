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

Reducir el tiempo y el esfuerzo dedicados a gestionar bajas y sustituciones en los servicios de ayuda a domicilio mediante una plataforma que facilite la consulta de turnos, la validación de disponibilidad y la asignación de un profesional, sentando las bases para mejorar la continuidad de la atención.

### 3.2. Objetivos específicos

1. **Agilizar la sustitución de un servicio.** Antes de la defensa final, conseguir que la persona coordinadora complete la identificación del turno afectado y la asignación de un candidato válido en un máximo de tres minutos y seis acciones principales de interfaz en, al menos, cuatro de cinco escenarios de prueba.
2. **Evitar asignaciones incompatibles.** Antes de la defensa final, lograr que el 100 % de las pruebas preparadas para comprobar conflictos de horario o falta de disponibilidad produzca el resultado esperado.
3. **Facilitar la aceptación de la sustitución.** Conseguir que, en al menos cuatro de cinco pruebas, el trabajador acepte la sustitución en menos de un minuto y que el estado del servicio se actualice correctamente.
4. **Validar la propuesta diferencial.** Antes de la defensa final, probar un prototipo de CUIDALIA Continuidad y de compatibilidad transparente; al menos dos de tres participantes deberán localizar el contexto de una visita anterior e identificar dos criterios de una recomendación en menos de un minuto.

Estos indicadores son criterios objetivo; no se presentan como resultados ya obtenidos. Las pruebas se harán con datos simulados y, si es posible, con la participación de una persona con experiencia en el SAD. Si no se dispone de profesionales para las pruebas, se indicará que los resultados se han obtenido con participantes de prueba.

### 3.3. Medición del éxito

| Objetivo | Indicador | Umbral de éxito | Comprobación |
|---|---|---|---|
| Agilizar sustituciones | Tiempo y acciones principales para asignar un sustituto. | 4 de 5 escenarios en ≤ 3 minutos y ≤ 6 acciones principales. | Prueba cronometrada de coordinación. |
| Evitar asignaciones incompatibles | Resultado de pruebas de disponibilidad y conflicto horario. | 100 % de los casos preparados produce el resultado esperado. | Pruebas de API y de interfaz con candidatos válidos e inválidos. |
| Facilitar la aceptación | Tiempo de aceptación y actualización de estado. | 4 de 5 pruebas en menos de un minuto con estado correcto. | Prueba completa de la vista de coordinación y la del trabajador. |
| Validar la diferenciación | Tiempo de localización de información y comprensión de criterios. | 2 de 3 participantes completan ambas tareas en menos de un minuto. | Prueba de un prototipo navegable. |

El objetivo original de medir el marcado de tareas en menos de 15 segundos podrá recuperarse cuando el checklist pase a formar parte del alcance implementado. No se evaluará como funcionalidad terminada del MVP si permanece fuera de la primera versión.

### 3.4. Plataforma

CUIDALIA se desarrollará como una aplicación web responsive con posibilidad de evolución a PWA. No se construirá una aplicación nativa independiente.

- **Escritorio:** interfaz principal para coordinación, optimizada para consultar turnos, filtrar servicios afectados y asignar sustituciones.
- **Móvil:** interfaz simplificada para que el trabajador consulte y acepte una sustitución. El acceso de familias y el registro de tareas se incorporarán en una iteración posterior.

La aplicación deberá funcionar en los navegadores de escritorio y móviles utilizados durante las pruebas. Las funciones instalables y las notificaciones push se verificarán por separado y no serán una dependencia del recorrido principal.

### 3.5. Usuarios y datos de prueba

El entorno de demostración se preparará con datos ficticios e inventados. Se contempla como volumen orientativo un conjunto de 2–3 cuentas de coordinación, unas 10 cuentas de trabajadores y entre 10 y 15 perfiles familiares para los escenarios previstos o las ampliaciones del prototipo. La primera versión funcional se centrará en los roles de coordinación y trabajador necesarios para completar la sustitución; no se considerará que el portal familiar está implementado únicamente por existir datos de prueba asociados a familiares.

Las direcciones y ubicaciones de ejemplo podrán situarse en San Fernando y alrededores, pero serán datos simulados y no identificarán domicilios reales de personas atendidas. No se utilizarán historias clínicas, medicaciones ni datos personales reales.

Los datos relativos a la salud son una categoría especial conforme al artículo 9 del Reglamento General de Protección de Datos. Por ello, el proyecto académico utilizará datos ficticios y se aplicarán controles por rol, limitación de acceso y minimización de los campos almacenados. Un posible uso real requeriría revisar la base jurídica del tratamiento, las responsabilidades correspondientes y las medidas de seguridad con asesoramiento adecuado.

Referencia normativa: [Reglamento (UE) 2016/679 (RGPD)](https://eur-lex.europa.eu/eli/reg/2016/679/oj?locale=es).

### 3.6. Lo que no haremos en esta versión

| Exclusión | Motivo |
|---|---|
| Generación automática o mediante IA de cuadrantes mensuales. | El MVP se centra en gestionar una baja y su sustitución; desarrollar un planificador completo aumentaría mucho el alcance. |
| Pasarelas de pago y facturación económica. | No son necesarias para el recorrido de sustitución y añaden requisitos técnicos y de seguridad. |
| Integración con sistemas de salud pública o historiales clínicos. | Requeriría autorizaciones, integraciones y controles ajenos al alcance académico. |
| Videollamadas integradas. | No resuelven el problema prioritario del MVP y aumentarían la complejidad. |
| Sincronización offline avanzada, colas distribuidas y Redis. | Para el alcance académico bastan el tratamiento de errores y, cuando corresponda, un estado de pendiente de envío con reintento sencillo. |
| Algoritmo avanzado de compatibilidad y ranking basado en matrices de rutas. | Primero se validará el recorrido básico; la integración de mapas se deja para una iteración posterior. |

### 3.7. Hoja de ruta posterior al MVP

Una vez completado y probado el recorrido de baja y sustitución, las ampliaciones se priorizarán según su valor para la continuidad del cuidado, el esfuerzo de desarrollo y la información obtenida de las pruebas.

1. **CUIDALIA Continuidad:** presentar un resumen breve del turno anterior, las tareas pendientes, las incidencias abiertas y las rutinas relevantes para el siguiente profesional.
2. **Registro de tareas e incidencias:** incorporar el checklist del trabajador y guardar observaciones operativas para consulta autorizada.
3. **Resumen diario para familias:** permitir que el familiar autorizado consulte el resultado del servicio registrado y los cambios pertinentes.
4. **Compatibilidad transparente:** empezar con filtros básicos y, posteriormente, comparar candidatos mediante criterios explicables. La disponibilidad y los requisitos obligatorios se comprobarán antes de cualquier puntuación.
5. **Detección explicable de patrones:** señalar repeticiones mediante reglas sencillas y mostrar qué registros originan cada aviso. Coordinación deberá revisar los avisos; no se generarán diagnósticos ni conclusiones clínicas.
6. **Notificaciones push y comunicación interna:** estudiar avisos push, chat y solicitudes familiares cuando los flujos básicos estén estables y se hayan verificado las limitaciones de las plataformas.
7. **CUIDALIA Autonomía:** evaluar con profesionales el registro de la ayuda prestada en actividades concretas y la utilidad de esa información para una atención centrada en la persona.
8. **Funciones complementarias:** valorar un botón SOS informativo e informes de horas para nóminas, siempre que se defina con precisión su alcance y no se comprometa la continuidad del cuidado.

Las prioridades podrán cambiar después de las entrevistas y pruebas. No se considera demostrado que estas capacidades sean exclusivas del producto; la diferenciación que se desea validar es la forma de conectarlas y explicar la información resultante.
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

