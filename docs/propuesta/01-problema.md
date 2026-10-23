# Cuidalia - Definición del Problema

## Introducción

**Cuidalia** es una plataforma web y móvil orientada a mejorar la coordinación de los servicios de ayuda a domicilio (SAD). Actualmente, las empresas del sector pueden recurrir a herramientas diferentes para gestionar los turnos, coordinar sustituciones, registrar tareas y comunicarse con las familias. Cuando la información está dispersa entre hojas de cálculo, llamadas, mensajes y documentos en papel, la gestión diaria puede volverse más lenta y aumentar el riesgo de errores.

Cuidalia busca reunir a coordinación, trabajadores y familiares en un mismo entorno. La propuesta incluye facilitar la gestión de cuadrantes y sustituciones, ofrecer a los profesionales una aplicación móvil para consultar sus servicios y registrar tareas, y habilitar un espacio para que las familias autorizadas puedan consultar la información disponible sobre la atención recibida. En caso de una baja, el sistema pretende ayudar a coordinación a localizar posibles sustitutos según criterios como disponibilidad, ubicación y adecuación a las necesidades de la persona atendida. Estas funcionalidades son la propuesta del proyecto y deberán ajustarse al alcance final del MVP.

## 1. La necesidad

### El problema

- **Coordinación ineficiente:** los coordinadores pueden depender de Excel, llamadas, WhatsApp, papel u otras herramientas desconectadas para gestionar cuadrantes, bajas y sustituciones.
- **Falta de información centralizada:** la información sobre usuarios, trabajadores, horarios, tareas e incidencias puede encontrarse dispersa en varios canales.
- **Problemas de comunicación:** la información entre coordinación, trabajadores y familiares puede perderse, llegar tarde o transmitirse de manera incorrecta.
- **Gestión complicada de imprevistos:** una baja o una urgencia puede obligar a realizar varias llamadas y modificaciones manuales antes de encontrar una solución.
- **Desplazamientos poco eficientes:** una planificación que no tenga en cuenta la ubicación y los horarios puede generar rutas poco optimizadas y tiempos de desplazamiento innecesarios.

### Quién lo sufre

El problema afecta a las distintas personas que intervienen en el servicio:

- **Empresa y coordinación:** gestionan cuadrantes, cambios de horario, bajas, sustituciones, incidencias, comunicación con trabajadores y familiares y seguimiento de los servicios. El uso de herramientas fragmentadas puede aumentar la carga administrativa y el riesgo de errores.
- **Trabajadores:** necesitan consultar sus servicios y horarios, registrar entradas y salidas, comunicar incidencias y dejar constancia de las tareas realizadas. Los cambios de última hora pueden generar incertidumbre y pérdida de tiempo.
- **Familiares:** pueden tener dificultades para conocer el estado del servicio, las tareas realizadas, las incidencias o los cambios de cuidador. Cuando necesitan información o realizar una petición, pueden acabar contactando con la empresa por teléfono.
- **Personas atendidas:** reciben directamente las consecuencias de los problemas de coordinación, por ejemplo, si se produce un retraso, un cambio de profesional o una falta de transmisión de información relevante.

### Frecuencia e impacto

La coordinación de cuadrantes, horarios, servicios e incidencias forma parte del trabajo habitual de una empresa de ayuda a domicilio. Sin embargo, **no se dispone todavía de datos cuantitativos que permitan afirmar con qué frecuencia se producen las bajas imprevistas, cuánto se tarda en cubrirlas o cuántos errores de comunicación se generan**. Por tanto, la frecuencia exacta debe validarse con profesionales del sector y no se presenta aquí como una estadística demostrada.

El impacto potencial varía según el perfil:

- **En la empresa:** una baja, un cambio de horario o una incidencia puede desencadenar varias llamadas y modificaciones manuales, lo que resta tiempo a otras tareas de coordinación.
- **En los trabajadores:** una comunicación tardía sobre un cambio de turno, las dificultades para registrar un servicio o la falta de un canal estructurado para comunicar incidencias pueden complicar la jornada laboral.
- **En familiares y personas atendidas:** la falta de información accesible puede generar incertidumbre sobre si el servicio se ha realizado, qué tareas se han completado o si ha ocurrido una incidencia. Esto es relevante porque el servicio está relacionado directamente con el cuidado y bienestar de una persona dependiente.

Para validar la frecuencia y el impacto, se propone recoger en entrevistas con profesionales datos como el número habitual de sustituciones, el tiempo medio necesario para gestionarlas, los canales utilizados y los problemas de comunicación más comunes.

### Evidencias

Como evidencia inicial se han revisado opiniones públicas de personas usuarias de servicios de ayuda a domicilio. Estas opiniones ayudan a identificar posibles problemas, pero son experiencias individuales y **no permiten estimar por sí solas la frecuencia del problema en todo el sector**.

- **Cuideo  Trustpilot:** en las opiniones públicas hay valoraciones positivas sobre la atención, la amabilidad y la claridad de la información. También aparece una reseña fechada el 17 de julio de 2026 en la que una persona describe dificultades durante el proceso de selección y afirma que no recibió aviso cuando una cuidadora causó baja ni contó con una sustituta en ese momento. Esta opinión es un ejemplo relacionado con la continuidad del servicio, no una prueba de que ocurra en todos los casos. [Consultar las opiniones de Cuideo en Trustpilot](https://es.trustpilot.com/review/cuideo.com?page=3).
- **HEMSA  Google Maps:** en las opiniones públicas del establecimiento consultadas por el equipo se identificó un comentario que describe problemas de puntualidad y dificultades para contactar con la empresa ante una incidencia relacionada con el servicio. El enlace disponible conduce al perfil y sus opiniones [Consultar HEMSA en Google Maps](https://www.google.com/maps/place/Hemsa/@36.4628724,-6.1940272,1225m/data=!3m1!1e3!4m8!3m7!1s0xd0dccd88c4595e7:0x3c0cf84d3203b874!8m2!3d36.4628724!4d-6.1940272!9m1!1b1!16s%2Fg%2F11xcm23w40?entry=ttu&g_ep=EgoyMDI2MDkzMC4wIKXMDSoASAFQAw%3D%3D).

Estas evidencias se utilizarán como punto de partida para formular preguntas de investigación y deberán complementarse, si es posible, con entrevistas a coordinadores, trabajadores y familiares.

## 2. Los usuarios

Los siguientes perfiles son **personas ficticias representativas** creadas para describir los principales roles de la aplicación. No corresponden a entrevistas reales ni deben interpretarse como resultados de una investigación ya realizada.

### Lucía, coordinadora de servicios

- **Quién es:** profesional encargada de organizar la plantilla y asignar los servicios dentro de una empresa de ayuda a domicilio. Gestiona varios trabajadores y usuarios a la vez y puede depender de herramientas y procesos manuales para organizar la jornada.
- **Necesidades:** crear y actualizar cuadrantes, localizar con rapidez posibles sustitutos para una baja y tener una visión general del estado de los servicios.
- **Frustraciones:** dedicar demasiado tiempo a resolver incidencias, depender de llamadas para gestionar bajas o cambios de turno y tener dificultades para cuadrar horarios, vacaciones y desplazamientos sin solapamientos.
- **Objetivos:** centralizar la gestión, consultar el estado de los servicios y reducir los errores en la asignación de personal.
- **Casos de uso:** crear y modificar cuadrantes, registrar una baja, consultar qué trabajadores están disponibles, revisar sugerencias de sustitución según disponibilidad, ubicación y adecuación al servicio y confirmar la asignación elegida.

### Carmen, familiar de una persona atendida

- **Quién es:** familiar que participa en el seguimiento de los cuidados de una persona dependiente y compagina esa responsabilidad con su vida personal y laboral.
- **Necesidades:** consultar la información disponible sobre la atención prestada, conocer las tareas registradas y disponer de un canal de comunicación para plantear peticiones.
- **Frustraciones:** no saber si el servicio se ha realizado o si ha ocurrido una incidencia y tener que contactar con la empresa para resolver consultas habituales.
- **Objetivos:** disponer de información clara y accesible sobre el servicio de su familiar y comunicarse con la empresa de forma más sencilla.
- **Casos de uso:** consultar el registro de las tareas realizadas y la información de medicación que haya sido registrada por el profesional y enviar una petición o nota relacionada con el servicio.

### Javier, trabajador de ayuda a domicilio

- **Quién es:** profesional que realiza visitas a distintos domicilios a lo largo de su jornada y necesita consultar la planificación de sus servicios.
- **Necesidades:** acceder a sus turnos y direcciones, registrar el inicio y el fin del servicio, consultar las tareas previstas y comunicar incidencias.
- **Frustraciones:** recibir tarde los cambios de turno, perder tiempo rellenando partes en papel o no disponer de un canal claro para dejar constancia de una incidencia.
- **Objetivos:** consultar la información de su jornada de manera sencilla y dedicar el máximo tiempo posible a la atención directa.
- **Casos de uso:** consultar su agenda diaria, registrar la entrada y la salida según las capacidades que finalmente se implementen, marcar las tareas como realizadas y comunicar incidencias a coordinación. La validación mediante geolocalización se considera una funcionalidad propuesta y deberá confirmarse dentro del alcance y los requisitos del proyecto.

## 3. La competencia

La siguiente comparativa es preliminar y recoge el análisis inicial del equipo. Las afirmaciones relativas a experiencia de uso, incidencias técnicas, precio o adaptación normativa deben contrastarse con documentación, demostraciones o reseñas concretas antes de presentarlas como conclusiones definitivas.

| Solución | Qué hace bien | Qué hace mal o qué limitaciones se deben comprobar |
|---|---|---|
| **GESAD** | Es una solución del sector SAD orientada a apoyar la gestión de servicios y tareas administrativas, incluida la gestión relacionada con entidades y administraciones. | En el análisis inicial del equipo se han señalado posibles dificultades de usabilidad y quejas sobre el fichaje mediante GPS, el uso con poca cobertura y la comunicación con las familias. Estos puntos deben respaldarse con reseñas concretas o pruebas de la aplicación. |
| **GESAD Mobile** ([información oficial](https://play.google.com/store/apps/details?id=gt.grupotrevenque.gesadmobile)) | Permite a trabajadores y coordinadores consultar agendas desde dispositivos móviles. Incluye fichaje de entrada y salida, seguimiento de las tareas realizadas, mensajería con el sistema central y encuestas de calidad. | Se debe comprobar mediante pruebas de uso la facilidad de navegación, el comportamiento en situaciones de cobertura limitada y la agilidad para gestionar cambios imprevistos. No se atribuyen carencias concretas sin evidencias verificables. |
| **ResiPlus SAD** | Según la revisión inicial del equipo, ofrece funciones para gestionar información de las personas atendidas y apoyar procesos del ámbito asistencial. | El equipo considera necesario comprobar si la modificación de cuadrantes y la reasignación ante bajas imprevistas pueden realizarse con suficiente agilidad, así como el alcance de las funciones disponibles para las familias. No se presentan esas limitaciones como verificadas. |
| **Birdie** | Cuenta con una interfaz orientada al uso digital y herramientas para que el personal registre información de sus visitas y tareas. | Antes de concluir que tiene limitaciones para el mercado español, deben verificarse su cobertura de los requisitos laborales y operativos del SAD en España, sus condiciones de precio para pequeñas empresas y su comportamiento con una conexión débil. |
| **ecoSoftWEB** ([información oficial](https://ecosoftconsulting.net/programas-para-empresas-de-ayuda-a-domicilio/)) | Es un ERP web especializado en ayuda a domicilio. Ofrece planificación de servicios, agendas de trabajadores, control horario mediante GPS, gestión de tareas y reasignación de servicios teniendo en cuenta factores como la disponibilidad, las ausencias, las necesidades de los usuarios y los desplazamientos. También permite generar informes para las familias o clientes. | Es necesario investigar mediante una demostración qué información pueden consultar las familias, cómo se comunica el contexto de una visita al siguiente profesional y qué grado de explicación ofrecen las recomendaciones de reasignación. No debe afirmarse que carece de estas funciones sin haberlo comprobado. |

### Oportunidades

- **Centralizar la operativa:** integrar en un mismo flujo a coordinación, auxiliares y familiares para reducir la dependencia de canales desconectados.
- **Facilitar las sustituciones:** estudiar cómo hacer más sencilla la revisión de candidatos y presentar claramente los motivos por los que un trabajador es adecuado para cubrir un servicio.
- **Favorecer la continuidad de la atención:** facilitar que la información relevante de cada visita esté organizada y disponible para los profesionales autorizados.
- **Mejorar la comunicación con las familias:** ofrecer información clara y accesible sobre los servicios realizados, las tareas registradas y las incidencias comunicadas.
- **Diseñar una experiencia móvil sencilla:** priorizar una interfaz accesible que facilite a los trabajadores consultar sus servicios y registrar las tareas con pocos pasos.

## 4. Propuesta de valor

> A las empresas de ayuda a domicilio especialmente a las personas coordinadoras les resulta difícil gestionar cuadrantes, cubrir bajas y mantener la información del servicio actualizada para trabajadores y familias. Hoy pueden utilizar programas de gestión junto con hojas de cálculo, llamadas, WhatsApp y papel, pero cuando la información queda repartida entre varios canales, la coordinación puede requerir trabajo manual y la comunicación puede llegar tarde. Cuidalia propone una plataforma que centraliza la gestión, ayuda a coordinación a localizar sustitutos teniendo en cuenta su disponibilidad y adecuación al servicio, ofrece a los trabajadores una aplicación para consultar su agenda y registrar tareas, y permite a las familias autorizadas consultar la información que se haya registrado sobre la atención recibida.
