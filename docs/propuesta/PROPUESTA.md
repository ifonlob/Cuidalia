# CUIDALIA — Propuesta de proyecto grupal

## Introducción

**CUIDALIA es una plataforma web adaptable para la coordinación de servicios de ayuda a domicilio (SAD)**. Su objetivo es facilitar la organización de turnos, la gestión de bajas y sustituciones y la transmisión de información entre coordinadores, profesionales de atención directa y familiares autorizados.

Las empresas de ayuda a domicilio deben coordinar horarios, disponibilidad de trabajadores, ausencias, visitas, tareas e incidencias. Cuando esta información se reparte entre hojas de cálculo, llamadas, mensajes y documentos en papel, una baja imprevista puede obligar a revisar varios registros, localizar a un sustituto, modificar el servicio y comunicar el cambio por distintos canales. Los trabajadores, por su parte, necesitan recibir la información operativa correcta antes de acudir a un domicilio, mientras que las familias pueden tener dificultades para consultar el estado de un servicio sin contactar con la oficina.

La investigación inicial del equipo incluye reseñas de usuarios que describen dificultades de coordinación, comunicación y sustitución. Estas evidencias ayudan a justificar la necesidad, aunque no permiten concluir que todos los servicios del sector sufran los mismos problemas. La frecuencia y el impacto deberán contrastarse en el futuro con profesionales del SAD.

CUIDALIA plantea reunir la operativa principal en un entorno conectado. La propuesta no consiste únicamente en digitalizar cuadrantes o tareas, sino en **relacionar la información registrada durante una visita con las decisiones que se toman después**. Su hipótesis de diferenciación se desarrolla en cuatro líneas: **CUIDALIA Continuidad**, que organiza la información relevante para el siguiente turno, detección explicable de patrones repetidos, recomendaciones transparentes de compatibilidad entre profesionales y personas atendidas y **CUIDALIA Autonomía**, como evolución centrada en la participación de la persona en las actividades cotidianas. Estas capacidades se plantean como una hoja de ruta y no como funcionalidades exclusivas del mercado ni como parte obligatoria de la primera versión.

Para mantener el proyecto dentro del tiempo disponible para un equipo de cuatro personas que está aprendiendo el stack MERN, el **Producto Mínimo Viable (MVP)** tendrá un alcance deliberadamente reducido. Se centrará en un recorrido completo: la persona coordinadora consulta los turnos, identifica un servicio afectado por una baja, comprueba qué trabajador está disponible, asigna la sustitución y verifica que el profesional la acepta. El trabajador participará únicamente en las acciones necesarias para completar ese recorrido. El fichaje, el registro de tareas y el resumen familiar serán funcionalidades posteriores, salvo que el equipo confirme que puede asumirlas sin poner en riesgo el núcleo del MVP.

El proyecto se desarrollará con **MongoDB, Express, React y Node.js (MERN)**. Se utilizarán datos ficticios durante el desarrollo y las pruebas, acceso diferenciado por roles y un modelo de datos inicial que pueda ampliarse conforme se incorporen nuevas capacidades. Las decisiones automáticas se limitarán a validaciones y reglas comprensibles: la plataforma no emitirá diagnósticos médicos y las recomendaciones futuras no sustituirán el criterio profesional de coordinación.

El equipo está formado por Daniel Espinosa, responsable de frontend, Irene Foncubierta, responsable de backend, Pablo Reyes, responsable de base de datos y Alejandro Espinosa, responsable de calidad y pruebas. El trabajo se organizará mediante GitHub Projects, issues, ramas de tarea y Pull Requests revisados por otra persona. El éxito se evaluará con pruebas cronometradas del recorrido principal, comprobaciones de las restricciones de disponibilidad y pruebas de usabilidad del prototipo de las funcionalidades diferenciales.

## 1. El problema y las personas destinatarias

### 1.1. Identificación de la necesidad

Las empresas de ayuda a domicilio deben coordinar de forma continua los turnos, las disponibilidades de los trabajadores, las ausencias, las sustituciones, las incidencias y la comunicación con las familias. Cuando esas tareas dependen de varias herramientas desconectadas, la información puede quedar duplicada, perderse o llegar tarde.

El problema resulta especialmente visible cuando una persona trabajadora comunica una baja. Coordinación debe identificar las visitas afectadas, comprobar qué candidatos pueden cubrirlas, evitar incompatibilidades horarias, actualizar el turno y confirmar que el sustituto conoce el servicio. Si parte de esta información está en Excel, otra en mensajes y otra en papel, la persona coordinadora debe reconstruir el contexto manualmente.

También existe una necesidad de continuidad entre visitas. El hecho de que una tarea o incidencia quede registrada no garantiza que la información sea fácil de encontrar para el siguiente profesional. Del mismo modo, varias observaciones que se repiten pueden pasar desapercibidas si es necesario revisar muchos registros manualmente. CUIDALIA estudiará cómo presentar ese contexto de manera estructurada y cómo señalar repeticiones observables sin convertirlas en conclusiones médicas.

La asignación de un profesional tampoco depende exclusivamente de su disponibilidad. En determinados servicios pueden ser relevantes la formación exigida, la experiencia, las preferencias de la persona atendida, la continuidad con profesionales que ya conocen sus rutinas y la viabilidad del desplazamiento. CUIDALIA plantea que una futura recomendación explique los criterios considerados para que coordinación pueda valorar el resultado.

### 1.2. Personas afectadas e impacto

- **Empresas y coordinación:** gestionan diariamente horarios, ausencias, cambios, sustituciones e incidencias. La fragmentación de herramientas puede aumentar la carga administrativa y el riesgo de errores.
- **Profesionales de atención directa:** necesitan consultar sus servicios, conocer la información operativa pertinente y recibir con suficiente antelación los cambios que afectan a su jornada.
- **Familiares autorizados:** necesitan información clara sobre la planificación, la finalización de los servicios y las incidencias relevantes, sin tener que llamar a la oficina para resolver cada consulta.
- **Personas atendidas:** son las principales beneficiarias del servicio. Necesitan que se respeten sus rutinas y preferencias y que la información relevante acompañe a los profesionales que las atienden.

### 1.3. Evidencias iniciales

La investigación inicial utiliza reseñas públicas como punto de partida:

- En las opiniones sobre [Cuideo en Trustpilot](https://es.trustpilot.com/review/cuideo.com), junto a valoraciones positivas sobre la atención, aparecen algunas quejas relacionadas con demoras en los procesos, sustituciones tras bajas y respuesta ante incidencias.
- En las reseñas de [Hemsa en Google Maps](https://www.google.com/maps/place/Hemsa/@36.4628724,-6.1940272,1225m/data=!3m1!1e3), una persona usuaria describe problemas de puntualidad y dificultades de comunicación con la empresa ante una situación delicada.

### 1.4. Personas usuarias

#### Persona 1. Coordinador o coordinadora

Es responsable de organizar los servicios, mantener actualizados los turnos, gestionar bajas y sustituciones y coordinar la comunicación entre la empresa, los profesionales y las familias.

- **Necesidades:** consultar rápidamente los turnos afectados, identificar trabajadores disponibles, comprobar las condiciones básicas del servicio y registrar la sustitución.
- **Frustraciones:** llamadas sucesivas, información repartida entre varias herramientas, solapamientos de horarios y dificultad para reconstruir el contexto antes de tomar una decisión.
- **Objetivos:** reducir el tiempo dedicado a los imprevistos, evitar asignaciones incompatibles y disponer de una visión clara del estado del servicio.
- **Casos de uso:** consultar y filtrar turnos, localizar un servicio afectado por una baja, comprobar la disponibilidad de candidatos, asignar un sustituto verificar la aceptación y, en futuras versiones, consultar contexto de visitas anteriores y avisos sobre patrones repetidos.

#### Persona 2. Profesional de atención directa

Realiza servicios en distintos domicilios y necesita información precisa para cumplir sus tareas, especialmente cuando sustituye a un compañero.

- **Necesidades:** consultar la agenda, conocer las indicaciones operativas pertinentes, aceptar cambios de turno y, en futuras iteraciones, registrar entradas, salidas, tareas e incidencias.
- **Frustraciones:** recibir cambios tarde, depender de mensajes dispersos y llegar a una visita sin conocer las rutinas relevantes.
- **Objetivos:** entender qué servicio debe realizar, disponer de los datos necesarios y dedicar el menor tiempo posible a tareas administrativas.
- **Casos de uso:** consultar una sustitución pendiente, aceptarla y verificar que el cambio ha quedado registrado y posteriormente, consultar el servicio, fichar y completar el registro de tareas.

#### Persona 3. Familiar autorizado

Compagina sus obligaciones personales y laborales con la supervisión de la atención de su familiar.

- **Necesidades:** conocer la planificación, consultar el resumen de un servicio finalizado y recibir información pertinente sobre cambios o incidencias.
- **Frustraciones:** incertidumbre sobre si se ha realizado una visita, qué tareas se han registrado o quién acudirá tras una sustitución.
- **Objetivos:** acceder a información clara sin realizar llamadas innecesarias y mantener una comunicación adecuada con la empresa.
- **Casos de uso:** en una versión posterior, consultar el resumen diario, conocer cambios autorizados de profesional y enviar solicitudes a coordinación.

#### La persona atendida como centro del servicio

La persona atendida puede no utilizar directamente la aplicación, pero sus necesidades deben orientar las decisiones. CUIDALIA debe ayudar a respetar sus preferencias y rutinas, limitar el acceso a la información sensible y evitar que los registros se conviertan en valoraciones automáticas sobre su salud o capacidad.

### 1.5. Análisis de la competencia

El análisis preliminar utiliza información pública de los proveedores. No se atribuyen debilidades técnicas que no hayan sido comprobadas de forma fiable.

#### GESAD Mobile

La documentación pública de [GESAD Mobile](https://play.google.com/store/apps/details?id=gt.grupotrevenque.gesadmobile) describe consulta de agendas, fichaje por domicilio, seguimiento de tareas y comunicación con el sistema central. Por tanto, CUIDALIA no presenta la agenda, el fichaje ni el registro de tareas como funciones exclusivas.

**Oportunidad que se investigará:** cómo relacionar la información de una visita con el relevo hacia el profesional siguiente y cómo presentar a coordinación la información contextual necesaria para resolver un imprevisto.

#### CIBERSAD

La información oficial de [CIBERSAD](https://cigesoc.es/cibersad/) describe funciones de planificación, control de asistencia, gestión de incidencias, trazabilidad y consulta de la evolución de las personas usuarias.

**Oportunidad que se investigará:** simplificar la consulta del contexto relevante entre visitas y presentar de forma explicable los patrones detectados a partir de los registros, sin afirmar que esas capacidades no existan ya en ninguna solución.

#### ecoSoftWEB

La información oficial de [ecoSoftWEB](https://ecosoftconsulting.net/programas-para-empresas-de-ayuda-a-domicilio/) describe planificación de tareas, control horario, geolocalización, seguimiento de usuarios y mecanismos de reasignación basados en parámetros como disponibilidad, zonas, rutas o trabajadores conocidos.

**Oportunidad que se investigará:** integrar los criterios de compatibilidad con el contexto del servicio, mostrar por qué se recomienda un candidato y mantener la decisión final en manos de coordinación.

#### Conclusión del análisis competitivo

Las soluciones del sector ya cubren numerosas funciones operativas. Por ello, CUIDALIA no pretende diferenciarse por la mera cantidad de apartados, sino por la hipótesis de conectar los datos registrados durante la atención con el contexto útil para el siguiente turno y con decisiones de coordinación que se puedan comprender y revisar. Esta hipótesis debe validarse con profesionales y mediante pruebas de prototipo.

### 1.6. Propuesta de valor diferencial

**CUIDALIA ayuda a las empresas de ayuda a domicilio a mantener la continuidad entre visitas y tomar decisiones de coordinación mejor fundamentadas, conectando el registro de las tareas con el contexto de cada persona, la detección explicable de patrones repetidos y la recomendación transparente de profesionales compatibles, siempre bajo supervisión humana.**

La propuesta se concreta en cuatro líneas de evolución:

1. **CUIDALIA Continuidad:** organiza las tareas realizadas, las que quedan pendientes, las incidencias abiertas y las rutinas relevantes en un resumen breve para el siguiente turno.
2. **Detección explicable de patrones:** aplica reglas comprensibles a los registros para señalar situaciones repetidas que coordinación debería revisar. No diagnostica ni interpreta clínicamente los cambios.
3. **Compatibilidad transparente:** comprueba primero los requisitos obligatorios del servicio y, en versiones posteriores, compara candidatos con criterios como disponibilidad, competencias, continuidad y desplazamiento, explicando los motivos de la recomendación.
4. **CUIDALIA Autonomía:** como evolución futura, permite reflejar el grado de ayuda prestada en determinadas actividades cotidianas, de forma respetuosa y sin generar puntuaciones generales ni diagnósticos automáticos.

El MVP se centrará en la gestión de la sustitución. Estas cuatro líneas forman la propuesta de diferenciación y la hoja de ruta posterior, no una promesa de que todas se implementarán en la primera entrega.

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
### 4.2. Responsables por módulo
### 4.3. Herramientas de desarrollo
### 4.4. Gestión del trabajo y flujo de Git
### 4.5. Comunicación y acuerdos
### 4.6. Riesgos organizativos y control de alcance
## 5. Conclusión
## Referencias técnicas principales
