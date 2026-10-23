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
### 4.2. Responsables por módulo
### 4.3. Herramientas de desarrollo
### 4.4. Gestión del trabajo y flujo de Git
### 4.5. Comunicación y acuerdos
### 4.6. Riesgos organizativos y control de alcance
## 5. Conclusión
## Referencias técnicas principales
