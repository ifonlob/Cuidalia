# Cuidalia - Definición del Problema

## Introducción

**Cuidalia** es una plataforma web y móvil creada para acabar con el descontrol en la gestión de la ayuda a domicilio. A día de hoy, las empresas del sector funcionan a base de parches: usan Excel para los turnos, cruzan llamadas a contrarreloj para cubrir una baja y los auxiliares apuntan las tareas en papel. Esto se traduce en coordinadores saturados , cuidadores con rutas mal planificadas y familias que no tienen ni idea de qué está pasando en la casa de sus mayores. 

Nuestra aplicación conecta a estas tres partes en un solo lugar. Más allá de quitar el papel, automatiza el trabajo duro del día a día. Si alguien se da de baja, el sistema cruza datos de ubicación y disponibilidad para proponer al sustituto ideal al momento. Para el trabajador, incluye una app sencilla pensada para fichar y reportar su ruta sin errores técnicos. Y para la familia, abre un portal donde pueden ver en directo las tareas hechas y la medicación administrada, evitando que tengan que llamar a la oficina cada dos por tres para quedarse tranquilos.

## 1. Identificación de la necesidad

### El Problema

**Coordinación ineficiente:** los coordinadores dependen de Excel, llamadas, WhatsApp, papel u otras herramientas desconectadas para gestionar cuadrantes, bajas y sustituciones.

**Falta de información:** la información sobre usuarios, trabajadores, horarios, tareas e incidencias se encuentra dispersa.

**Problemas de comunicación:** la información entre coordinador, trabajador y familia puede perderse, llegar tarde o transmitirse de manera incorrecta.

**Gestión complicada de imprevistos:** una baja o una urgencia obliga a realizar múltiples llamadas y modificaciones manuales para encontrar una solución. 

**Desplazamientos ineficientes:** la planificación de los servicios puede generar rutas poco optimizadas y tiempos de desplazamiento innecesarios.

### ¿A quién afecta y con qué frecuencia?

Esto afecta a todas las personas involucradas en el proceso, tanto a la empresa como a los trabajadores y clientes.

**La empresa:** Gestionan continuamente cuadrantes, cambios de horarios, bajas, sustituciones, incidencias, comunicación con trabajadores y familiares y seguimiento de los servicios. La utilización de herramientas fragmentadas aumenta la carga administrativa y el riesgo de errores.

**Trabajadores:** Necesitan consultar sus servicios y horarios, registrar entradas y salidas, comunicar incidencias y dejar constancia de las tareas realizadas. Los cambios de última hora pueden generar incertidumbre y pérdida de tiempo.

**Familiares y dependientes:** Pueden tener dificultades para conocer el estado del servicio, las tareas realizadas, incidencias o cambios de cuidador. Cuando necesitan información o realizar una petición, frecuentemente deben contactar con la empresa.


### Impacto

**En la empresa:** Es probablemente donde el problema tiene un impacto operativo más directo. Los coordinadores tienen que gestionar simultáneamente múltiples servicios, trabajadores y usuarios. Una baja, un cambio de horario o una incidencia puede desencadenar varias llamadas y modificaciones manuales.

**En los trabajadores:** Los cuidadores son quienes ejecutan el servicio y necesitan disponer de información actualizada. Una comunicación tardía de un cambio de turno, dificultades para registrar el servicio o la ausencia de un canal estructurado para comunicar incidencias pueden afectar directamente a su jornada laboral. 

**En familiares y dependientes:** El impacto se manifiesta principalmente en forma de falta de visibilidad e incertidumbre. El familiar puede no saber si el servicio se ha realizado, qué tareas se han llevado a cabo o si ha ocurrido alguna incidencia sin tener que contactar con la empresa.

Esto es especialmente relevante porque el servicio afecta directamente al bienestar y cuidado de una persona dependiente, por lo que disponer de información clara y accesible tiene un valor importante para el familiar.


### Evidencias

En la empresa [Cuideo](https://es.trustpilot.com/review/cuideo.com) se observa una valoración generalmente muy positiva de la empresa. Los usuarios destacan especialmente la amabilidad, cercanía y rapidez del personal, así como su capacidad para atender las necesidades particulares de cada caso y proporcionar presupuestos de manera ágil. También se valora positivamente la atención ofrecida por los diferentes profesionales, quienes proporcionan asesoramiento personalizado, explican las distintas alternativas con claridad y resuelven las dudas de forma profesional.
No obstante, algunas opiniones reflejan determinados aspectos susceptibles de mejora. Entre ellos, se señalan los largos tiempos asociados al proceso de selección y las dificultades para gestionar sustituciones cuando se producen bajas de cuidadoras. Asimismo, algunos clientes indican que determinadas incidencias imprevistas no siempre reciben una respuesta con la rapidez esperada, especialmente cuando requieren contactar con el servicio de atención telefónica.

En la empresa [Hemsa](https://www.google.com/maps/place/Hemsa/@36.4628724,-6.1940272,1225m/data=!3m1!1e3!4m8!3m7!1s0xd0dccd88c4595e7:0x3c0cf84d3203b874!8m2!3d36.4628724!4d-6.1940272!9m1!1b1!16s%2Fg%2F11xcm23w40?entry=ttu&g_ep=EgoyMDI2MDkzMC4wIKXMDSoASAFQAw%3D%3D) una clienta denuncia graves problemas de coordinación y comunicación en el servicio de ayuda a domicilio. En concreto, el cuidador llegó tarde a recoger a su hermano, una persona totalmente dependiente, y lo dejó esperando en un lugar desconocido. Además, la familia tuvo dificultades para contactar con la empresa pese a realizar numerosas llamadas y considera que la coordinadora mostró falta de empatía y una respuesta inadecuada ante una situación de urgencia.

## 2. Definición de usuarios objetivo

### User Persona 1: El Coordinador
Es el profesional encargado de la organización de la plantilla y asignación de servicios dentro de la empresa de ayuda a domicilio. Maneja un volumen alto de empleados y clientes simultáneos, y actualmente depende de herramientas genéricas y procesos manuales para la organización diaria.

**Necesidades:** Automatizar la creación y actualización de cuadrantes, localizar rápidamente perfiles idóneos para sustituciones de última hora y optimizar el flujo de trabajo de toda la plantilla.

**Frustraciones:** Consumo excesivo de tiempo resolviendo incidencias, alta dependencia de llamadas telefónicas para gestionar bajas o cambios de turno, y dificultad para cuadrar horarios, vacaciones y desplazamientos sin generar problemas de solapación de horarios.

**Objetivos:** Centralizar la gestión, obtener una visión global y en tiempo real del estado de los servicios, y minimizar el margen de error humano en la asignación de personal.

**Casos de uso principales:** 

  * Crear, modificar y supervisar cuadrantes de trabajo de forma dinámica.
  * Poder usar un algoritmo de compatibilidad para emparejar al trabajador más adecuado con las necesidades de cada usuario.
  * Calcular y optimizar las rutas de desplazamiento de los empleados.

### User Persona 2: El Familiar del Usuario
Es la persona responsable del usuario, la cual compagina su vida personal y obligaciones laborales con la supervisión de los cuidados de su familiar.

**Necesidades:** Obtener visibilidad y constancia en tiempo real sobre la atención prestada, confirmar la correcta administración de tratamientos y disponer de un canal de comunicación directo y eficiente.

**Frustraciones:** Incertidumbre sobre el estado diario de su familiar, malentendidos en la transmisión de pautas médicas o alimenticias, y la ineficiencia de tener que pasar siempre a través de la centralita administrativa para consultas básicas o cambios menores.

**Objetivos:** Lograr total tranquilidad mental, asegurando un seguimiento exhaustivo y una comunicación fluida sin intermediarios innecesarios.

**Casos de uso principales:** 

  * Consultar el registro actualizado de tareas realizadas y medicación suministrada en cada visita a su familiar.
  * Añadir peticiones específicas, recordatorios o notas en tiempo real para el cuidador asignado en el turno correspondiente.

### User Persona 3: El Trabajador
Es el profesional que realiza múltiples visitas a diferentes domicilios a lo largo de su jornada laboral, enfrentándose a un entorno de trabajo dinámico y a menudo impredecible.

**Necesidades:** Disponer de un registro claro y accesible de sus rutas y tareas por domicilio, simplificar el control de su jornada laboral y contar con un chat para reportar cualquier incidencia.

**Frustraciones:** Recepción tardía de notificaciones sobre cambios imprevistos en sus turnos o usuarios, pérdida de tiempo rellenando partes de trabajo en papel, y dificultades para dejar constancia formal de incidencias o urgencias médicas de forma ágil.

**Objetivos:** Centrar su esfuerzo y atención exclusivamente en el cuidado del usuario, delegando toda la carga administrativa y de cuadrantes a la aplicación móvil.

**Casos de uso principales:** 

  * Registrar el fichaje de entrada y salida mediante validación geolocalizada.
  * Visualizar su ruta diaria y marcar las tareas como completadas en cada domicilio.
  * Notificar urgencias, incidencias o alertas directamente a la coordinación y a los familiares.

## 3. Análisis de competencia

### Competidor 1: Gesad
* **Fortalezas:** Es el estándar en España para licitaciones públicas y grandes concesionarias. Resuelve bien la parte legal, convenios del sector y facturación con la administración.
* **Debilidades:** La interfaz esta anticuada y  es poco intuitiva. En las tiendas de apps, las auxiliares reportan fallos constantes al registrar el fichaje por GPS, pérdidas de datos sin cobertura y una desconexión con las familias que no tienen acceso a la plataforma.

### Competidor 2: ResiPlus SAD
* **Fortalezas:** Buen control del expediente clínico y sanitario del usuario, respaldado por un soporte técnico asentado en el sector asistencial español.
* **Debilidades:** La gestión de cuadrantes es muy rígida y reorganizar turnos por bajas imprevistas requiere procesos manuales lentos. Es un software de escritorio adaptado a la web con mal rendimiento, y su zona de familias es un simple buzón de documentos sin seguimiento en tiempo real.

### Competidor 3: Birdie
* **Fortalezas:** Interfaz limpia y moderna. La aplicación móvil es ágil y facilita que el cuidador registre tareas e incidencias durante la visita sin complicaciones.
* **Debilidades:** Está orientada al mercado ingles, por lo que no contempla la normativa laboral ni los convenios del SAD en España. Además, el precio por usuario es elevado para pymes y la sincronización se congela con mala cobertura.

### Oportunidades
* **Centralizar la operativa:** Unir en un mismo flujo a coordinación, auxiliares y familiares para no depender de llamadas telefónicas ni parches por WhatsApp.
* **Reasignación rápida de bajas:** Sugerir sustitutos de forma automática cruzando cercanía física, disponibilidad horaria y perfil adecuado para el dependiente.
* **Muro informativo para la familia:** Mostrar en directo la llegada del auxiliar, tareas completadas y medicación administrada para reducir llamadas de consulta a la centralita.
* **App de campo funcional:** Diseñar una vista móvil ligera donde fichar y marcar tareas tome dos toques, pensada para trabajadores con poca destreza tecnológica.

### Punto de control
Se decide **continuar con la idea candidata**. El software actual en España está enfocado en la facturación y la burocracia, dejando tirada la coordinación diaria y la tranquilidad familiar. Existe un hueco claro para una solución ágil, accesible y construida con una arquitectura web moderna.

### Propuesta de valor única
A las **empresas de ayuda a domicilio** les pasa que **pierden horas al día cuadrando turnos a mano, tapando bajas de imprevisto por teléfono y atendiendo a familias con dudas sobre el servicio**.

Hoy usan **ERPs tradicionales rígidos combinados con hojas de Excel y grupos de WhatsApp**, que fallan en **la falta de automatización, apps móviles que dan errores al fichar y nula información en tiempo real para las familias**.

Nosotros les damos **una plataforma web integral que sugiere sustituciones por cercanía y compatibilidad, permite a los auxiliares fichar y reportar tareas en dos toques desde el móvil, y da a las familias visibilidad directa sobre el cuidado de su familiar sin saturar la centralita**.

## 4. Propuesta de Valor Única

A **las empresas de ayuda a domicilio y las familias de los usuarios** le pasa **que el día a día es un caos organizativo. La oficina pierde horas cuadrando turnos a mano o cubriendo bajas urgentes por teléfono, y los familiares sufren la angustia de no saber a qué hora llegó el cuidador o si le dio la medicación al abuelo.** 

Hoy usa **software anticuado mezclado con hojas de Excel, papel y grupos de WhatsApp**, que falla en **que nada está conectado en tiempo real. Si hay una urgencia, los programas no ayudan a buscar sustitutos, las apps para que el trabajador fiche fallan si hay mala cobertura, y las familias están totalmente aisladas del proceso a no ser que llamen a la centralita.** 

Nosotros le damos **una plataforma  que automatiza las sustituciones sugiriendo al cuidador más cercano y compatible, da a los trabajadores una app donde fichar y marcar tareas en dos toques, y abre un muro en directo para que las familias vean cómo está su familiar sin tener que contactar con la empresa.**
