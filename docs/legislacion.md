# Legislación y cumplimiento normativo de CUIDALIA
## 1. Introducción y alcance
CUIDALIA es una plataforma web orientada a centralizar la coordinación de servicios de ayuda a domicilio. Entre las funciones previstas se encuentran gestionar sustituciones, consultar información operativa de la persona atendida, registrar la entrada y salida del profesional, completar tareas del servicio, registrar incidencias y generar resúmenes para familiares autorizados.
Cabe destacar que durante el desarrollo y las demostraciones se utilizarán datos ficticios, es decir, no se introducirán nombres, domicilios, teléfonos, patologías, medicación, ubicaciones ni partes de servicio de personas reales.
## 2. Normativa identificada
| Norma o referencia | Aplicación a CUIDALIA | Medidas principales |
|---|---|---|
| [Reglamento General de Protección de Datos (RGPD), Reglamento (UE) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj?locale=es) | Aplicable si se tratan datos personales de personas en la UE. Los datos de salud tienen protección reforzada. | Determinar la base jurídica; informar de forma transparente; proteger los datos; atender derechos; documentar el tratamiento y valorar una evaluación de impacto. |
| [Ley Orgánica 3/2018 (LOPDGDD)](https://www.boe.es/eli/es/lo/2018/12/05/3/con) | Complementa el RGPD en España. Es especialmente relevante para los datos laborales y la geolocalización de trabajadores. | Información previa sobre geolocalización, garantías de intimidad y aplicación de los derechos digitales. |
| [Ley 34/2002 de servicios de la sociedad de la información y de comercio electrónico (LSSI-CE)](https://www.boe.es/eli/es/l/2002/07/11/34/con) | Relevante para la prestación de un servicio web con finalidad económica, sus comunicaciones comerciales y las cookies o tecnologías similares. | Información legal del prestador, reglas de comunicaciones comerciales y consentimiento para cookies no exentas. |
| [Real Decreto Legislativo 2/2015, Estatuto de los Trabajadores](https://www.boe.es/eli/es/rdlg/2015/10/23/2/con) y [Real Decreto-ley 8/2019](https://www.boe.es/eli/es/rdl/2019/03/08/8/con) | Relevantes si el fichaje de CUIDALIA se utiliza como registro diario de jornada laboral. | Registrar inicio y final de la jornada y conservar los registros durante cuatro años cuando se trate del registro laboral exigido por el Estatuto. |
| [Ley 11/2023, de accesibilidad de determinados productos y servicios](https://www.boe.es/buscar/act.php?id=BOE-A-2023-11022) | Puede aplicar si el servicio y el modelo comercial entran en su ámbito. La propia ley contempla una exención para microempresas que prestan servicios. | Analizar el ámbito legal concreto y, cuando corresponda, cumplir los requisitos de accesibilidad aplicables. |
| [Real Decreto 1112/2018 sobre accesibilidad del sector público](https://www.boe.es/eli/es/rd/2018/09/07/1112) | Se aplica a sitios web y aplicaciones del sector público y otros sujetos incluidos en su ámbito, no automáticamente a toda aplicación privada. | Requisitos de accesibilidad y revisiones para las entidades obligadas. |
| [Real Decreto Legislativo 1/1996, Ley de Propiedad Intelectual](https://www.boe.es/eli/es/rdlg/1996/04/12/1/con) | Aplicable al código, documentación, diseños y recursos originales o de terceros utilizados en la plataforma. | Respetar derechos de autor, licencias de dependencias, imágenes, iconos, fuentes y otros recursos. |
| [Ley 9/2016 de Servicios Sociales de Andalucía](https://www.boe.es/eli/es-an/l/2016/12/27/9/con) | Puede ser relevante para las entidades que prestan servicios sociales o de ayuda a domicilio en Andalucía. No se presupone que todas sus obligaciones recaigan directamente sobre el proveedor tecnológico. | Verificar las obligaciones sectoriales de la entidad prestadora y cualquier requisito derivado de contratos o autorizaciones del servicio. |
La tabla identifica el marco inicial. Antes de utilizar CUIDALIA en una organización real habrá que confirmar el alcance de cada norma a partir de la actividad concreta, el tipo de cliente, el contrato y los datos efectivamente tratados.
## 3. Protección de datos personales: RGPD y LOPDGDD
### 3.1. Datos que podría tratar CUIDALIA
| Categoría | Ejemplos del proyecto | Riesgo y precaución |
|---|---|---|
| Identificación y contacto | Nombre, datos de contacto y cuenta de usuario. | Limitar los campos a los necesarios para cada función. |
| Datos del servicio y del domicilio | Domicilio donde se presta la ayuda, horarios, turnos y servicio asignado. | El acceso debe estar limitado a las personas autorizadas para ese servicio. |
| Datos de salud | Patologías, alergias, medicación y necesidades de asistencia. | Son datos de categoría especial conforme al artículo 9 del RGPD. Requieren una base del artículo 6 y una condición válida del artículo 9. |
| Datos laborales | Identidad del trabajador, asignaciones, aceptación de sustituciones y registros de visita. | Definir finalidades claras y limitar el acceso a la información laboral. |
| Geolocalización | Posición asociada al fichaje de entrada o salida. | Informar previamente, justificar la finalidad y evitar el seguimiento fuera del contexto necesario. |
| Información de incidencias y tareas | Tareas completadas, tareas pendientes, incidencias y observaciones operativas. | Evitar comentarios excesivos, datos irrelevantes y opiniones no verificadas. |
### 3.2. Responsable y encargado del tratamiento
Antes de poner la aplicación en producción se deberá definir por contrato quién determina las finalidades y los medios del tratamiento:
- **Empresa o entidad de ayuda a domicilio:** normalmente será la responsable del tratamiento de los datos de las personas atendidas y de sus trabajadores cuando determine para qué se utilizan y cómo se organiza el servicio.
- **CUIDALIA como proveedor de software:** si trata los datos únicamente siguiendo las instrucciones del cliente, normalmente actuará como encargado del tratamiento. Deberá existir un contrato conforme al artículo 28 del RGPD, con instrucciones, confidencialidad, medidas de seguridad, gestión de incidencias, subencargados, asistencia en derechos y devolución o eliminación de datos al finalizar el servicio.
- **CUIDALIA como responsable independiente:** si en el futuro decide utilizar datos para finalidades propias, habrá que evaluar esa finalidad y su base jurídica de forma separada. No podrá asumirse que el contrato de encargado cubre cualquier uso.
Esta asignación debe reflejarse en la política de privacidad y en los contratos; no basta con elegir una etiqueta en la documentación.
### 3.3. Base jurídica y datos de salud
Para cada finalidad se deberá identificar una base jurídica válida del artículo 6 del RGPD. Además, cuando se traten datos relativos a la salud, deberá concurrir una de las condiciones que permiten el tratamiento de categorías especiales del artículo 9.
**No se debe considerar que marcar una casilla de aceptación de las condiciones legaliza automáticamente todos los tratamientos.** El consentimiento explícito puede ser una condición válida en determinados casos, pero no es necesariamente la base adecuada para todas las operaciones. La entidad que actúe como responsable tendrá que determinar la base y, si procede, la condición del artículo 9 que corresponden al servicio real.
Medidas propuestas:
- Documentar las finalidades por separado: gestión de usuarios, asignación de visitas, coordinación del servicio, registro de jornada si corresponde, comunicación con familiares y gestión de incidencias.
- Recoger solo los datos imprescindibles para cada finalidad y perfil.
- No utilizar información de salud para publicidad, analítica comercial ni finalidades incompatibles.
- No tratar datos reales en el entorno académico, salvo que exista una autorización y un marco de cumplimiento verificados; para la entrega del proyecto se utilizarán datos sintéticos.
- Evitar que el personal vea por defecto toda la información de todas las personas atendidas.
### 3.4. Información transparente y política de privacidad
La información de privacidad debe estar redactada de manera clara, accesible y fácil de localizar. Según la operación de tratamiento, deberá incluir como mínimo:
- Identidad y datos de contacto del responsable.
- Datos de contacto del delegado de protección de datos, si existe o debe designarse.
- Finalidades y bases jurídicas del tratamiento.
- Categorías de datos tratados y, cuando proceda, destinatarios.
- Información sobre transferencias internacionales, si las hubiera.
- Plazos de conservación o criterios utilizados para determinarlos.
- Derechos de las personas y forma de ejercerlos.
- Derecho a reclamar ante la [Agencia Española de Protección de Datos (AEPD)](https://www.aepd.es/).
- Información sobre decisiones automatizadas o elaboración de perfiles, si en el futuro se incorporan.
Los textos finales no deben conservar marcadores genéricos: se completarán con la identidad real de la entidad responsable, los proveedores usados, las finalidades definitivas y los plazos aplicables.
### 3.5. Derechos de las personas usuarias
CUIDALIA deberá contar con un procedimiento para recibir, verificar y tramitar las solicitudes de derechos. Según el caso, las personas podrán solicitar acceso, rectificación, supresión, limitación, portabilidad u oposición, sin perjuicio de los límites legales que correspondan.
Se propone implementar en la cuenta o mediante un canal de solicitud las siguientes funciones:
- **Consultar los datos personales** asociados a la cuenta.
- **Exportar los datos en JSON** en un formato estructurado que pueda entregarse a la persona solicitante.
- **Solicitar la eliminación de la cuenta y los datos**, con verificación de identidad y revisión de las obligaciones legales de conservación.
- **Registrar y seguir las solicitudes** para comprobar los plazos de respuesta.
La eliminación no debe ejecutarse de forma indiscriminada cuando existan datos que deban conservarse por una obligación legal o para la formulación, el ejercicio o la defensa de reclamaciones. En esos casos, se limitará el tratamiento y se explicará el motivo a la persona afectada.
### 3.6. Seguridad de la información
El RGPD exige medidas técnicas y organizativas adecuadas al riesgo. Para CUIDALIA se proponen las siguientes medidas de diseño y desarrollo:
| Medida | Implementación prevista |
|---|---|
| Contraseñas protegidas | No almacenar contraseñas en texto plano. Utilizar un algoritmo de hash de contraseñas adecuado, como bcrypt con una configuración segura, o una alternativa moderna equivalente. |
| Comunicaciones seguras | Utilizar HTTPS/TLS en todos los entornos publicados y no transmitir credenciales o datos sensibles en texto plano. |
| Control de acceso por roles | Separar los permisos de coordinación, trabajador y familiar. Validar los permisos en el backend, no solo ocultar botones en React. |
| Acceso por servicio y persona atendida | Comprobar en cada petición que el usuario tiene autorización para consultar o modificar ese registro concreto. |
| Gestión de sesiones | Proteger tokens y sesiones, establecer expiración y revocación y evitar guardar secretos en el repositorio. |
| Registro de actividad | Registrar accesos y acciones relevantes de forma proporcional, evitando copiar datos de salud innecesarios en los logs. |
| Copias de seguridad | Definir copias, acceso restringido y pruebas periódicas de restauración. |
| Configuración y secretos | Usar variables de entorno y un gestor de secretos. No subir contraseñas, tokens, claves ni datos reales a GitHub. |
| Actualizaciones | Mantener dependencias del stack MERN actualizadas y revisar vulnerabilidades conocidas. |
| Entornos separados | Separar desarrollo, pruebas y producción. Las pruebas académicas usarán datos ficticios. |
| Gestión de incidentes | Definir un procedimiento para detectar, registrar, investigar y responder a brechas de seguridad. |
El responsable deberá notificar una violación de seguridad a la autoridad de control cuando corresponda, dentro de los plazos previstos por el RGPD -por regla general, sin dilación indebida y, si es posible, en un máximo de 72 horas desde que tenga constancia cuando exista riesgo para los derechos y libertades-. Cuando proceda, también deberá informar a las personas afectadas.
### 3.7. Análisis de riesgos, evaluación de impacto y delegado de protección de datos
Antes de tratar datos reales se realizará un análisis de riesgos. Como CUIDALIA podría combinar datos de salud, información sobre personas en situación de dependencia, datos laborales y geolocalización, el equipo deberá valorar formalmente si el tratamiento puede entrañar un alto riesgo.
Si el análisis concluye que es probable que el tratamiento entrañe un alto riesgo para los derechos y libertades, se realizará una **Evaluación de Impacto relativa a la Protección de Datos (EIPD)** antes de iniciar el tratamiento. El tratamiento a gran escala de categorías especiales de datos es uno de los supuestos que debe tenerse en cuenta. Por el tipo de información prevista, se recomienda evaluar la necesidad de una EIPD antes de cualquier despliegue real, sin afirmar que siempre resulte obligatoria con independencia del volumen y del uso.
El nombramiento de un **Delegado de Protección de Datos (DPD/DPO)** no se presume obligatorio por el mero hecho de tratar algún dato de salud. Debe comprobarse si la actividad principal implica, por ejemplo, tratamiento a gran escala de categorías especiales, o si se da otro supuesto legal de designación obligatoria.
Recursos de referencia:
- [RGPD - texto oficial en español](https://eur-lex.europa.eu/eli/reg/2016/679/oj?locale=es)
- [AEPD - medidas para cumplir la normativa de protección de datos](https://www.aepd.es/preguntas-frecuentes/2-tus-obligaciones-como-responsable-del-tratamiento/3-que-obligaciones-establece-el-rgpd-para-los-responsables/FAQ-0219-que-medidas-tengo-que-adoptar-para-cumplir-con-la-normativa)
- [AEPD - evaluación de impacto](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/realizacion-de-evaluaciones-de)
- [AEPD - protección de datos desde el diseño](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/proteccion-de-datos-desde-el-diseno)
## 4. Geolocalización y registro de jornada de los trabajadores
CUIDALIA contempla un fichaje de entrada y salida vinculado al domicilio del servicio. Si se utiliza la geolocalización, se tratarán datos personales que deben limitarse a una finalidad concreta y proporcionada.
El artículo 90 de la LOPDGDD establece garantías para el uso de sistemas de geolocalización en el ámbito laboral. La empresa empleadora deberá informar a los trabajadores, de forma expresa, clara e inequívoca y con carácter previo, de la existencia y características del sistema y de los derechos que pueden ejercer.
Medidas propuestas:
- Utilizar la ubicación solo para la finalidad informada, por ejemplo, validar el fichaje de entrada o salida del servicio.
- Solicitar la ubicación únicamente en el momento necesario; no mantener un seguimiento continuo cuando no sea imprescindible ni justificado.
- Informar de qué dato se obtiene, cuándo se recoge, quién lo consulta, para qué se utiliza y cuánto tiempo se conserva.
- Restringir el acceso a los registros de fichaje a los perfiles que lo necesiten.
- No mostrar la ubicación exacta a familiares si no es necesaria para la finalidad y no existe una base válida para esa comunicación.
- Probar la experiencia con una ubicación simulada y no publicar coordenadas reales.
Cuando los registros de CUIDALIA tengan la finalidad de cumplir con el registro diario de jornada del artículo 34.9 del Estatuto de los Trabajadores, deberán incluir el horario concreto de inicio y fin y conservarse durante **cuatro años**, quedando a disposición de las personas trabajadoras, sus representantes legales y la Inspección de Trabajo y Seguridad Social, en los términos de la norma.
No debe confundirse automáticamente el registro de una visita asistencial con el registro legal de jornada: la empresa cliente debe decidir y documentar si el sistema cubre ambas finalidades y comprobar que los registros cumplen los requisitos laborales aplicables.
## 5. Política de cookies y tecnologías similares
La LSSI-CE regula, entre otras materias, el almacenamiento y recuperación de información en los dispositivos de los usuarios. Las cookies estrictamente necesarias para prestar un servicio expresamente solicitado pueden quedar exentas de consentimiento, pero las cookies analíticas, publicitarias o de seguimiento no exentas requieren, con carácter general, información clara y consentimiento válido previo.
### Requisitos para el banner
- Mostrar la información esencial y un enlace visible a la política de cookies.
- Ofrecer **Aceptar** y **Rechazar** con una visibilidad y facilidad comparables, además de una opción **Configurar** cuando proceda.
- No activar cookies no necesarias antes de obtener consentimiento.
- Permitir retirar o modificar el consentimiento posteriormente.
- Registrar las preferencias de forma proporcional y no usar casillas premarcadas como consentimiento.
- Identificar en la política las cookies o tecnologías utilizadas, su finalidad, titular, duración y si pertenecen a terceros.
- Revisar las cookies reales con las herramientas del navegador antes de publicar el banner; no se debe inventar un listado de cookies que no se haya comprobado.
Si el MVP utiliza únicamente cookies técnicas estrictamente necesarias para autenticar la sesión y mantener la seguridad, puede que no necesite un banner de consentimiento para esas cookies. Aun así, se documentará su uso y se comprobará si existen cookies o tecnologías adicionales introducidas por analítica, fuentes, mapas, servicios de terceros u otras integraciones.
Referencia: [AEPD - Guía sobre el uso de las cookies, mayo de 2024](https://www.aepd.es/es/documento/guia-cookies.pdf).
## 6. Condiciones de uso y términos del servicio
CUIDALIA debe disponer de condiciones adaptadas a su funcionamiento real. El documento no debe limitarse a una plantilla genérica: debe explicar el propósito de la plataforma, los perfiles disponibles, el uso permitido y las limitaciones relevantes.
Las condiciones deberán concretar, según el modelo comercial definitivo:
- Identificación del prestador del servicio y datos de contacto.
- Finalidad y características principales de la plataforma.
- Requisitos de registro, autenticación y uso de cuentas.
- Responsabilidades de los usuarios y reglas de uso aceptable.
- Obligaciones del cliente respecto a la licitud, exactitud y actualización de los datos que introduce.
- Gestión de permisos, cuentas, incidencias, disponibilidad y mantenimiento.
- Propiedad intelectual del software, documentación y materiales.
- Condiciones de suspensión, terminación, exportación y devolución de datos.
- Limitaciones de responsabilidad redactadas de acuerdo con la legislación aplicable, sin intentar excluir derechos irrenunciables.
- Enlace a privacidad y cookies.
CUIDALIA apoya la coordinación, pero no debe presentarse como sustituto del criterio profesional, de los protocolos de la entidad prestadora ni de los servicios de emergencia. Las futuras recomendaciones de compatibilidad o avisos de patrones deberán ser explicables y revisables por una persona responsable; no se presentarán como diagnósticos médicos ni como decisiones clínicas.
Si en el futuro se contratan suscripciones, se ofrecen pagos o se permite contratar directamente a consumidores, deberán revisarse también las obligaciones contractuales, de información precontractual y de consumidores que resulten aplicables al modelo concreto.
## 7. Accesibilidad web
La accesibilidad es especialmente relevante porque CUIDALIA está destinada a conectar a profesionales y familiares y puede ser utilizada por personas mayores o con distintas capacidades. El proyecto tomará como objetivo técnico **WCAG 2.1 nivel AA**, tal como plantea el criterio de evaluación, y revisará la normativa obligatoria que corresponda al tipo de proveedor y servicio.
La obligación legal no es idéntica para todas las webs privadas. El Real Decreto 1112/2018 se dirige al sector público y otros sujetos incluidos en su ámbito. La Ley 11/2023 regula determinados productos y servicios y contempla una exención para microempresas que prestan servicios. Por tanto, se comprobará la aplicación concreta de estas normas según el modelo de negocio; en cualquier caso, el proyecto adoptará WCAG 2.1 AA como referencia de diseño y calidad.
### Requisitos de diseño y pruebas
- Contraste suficiente entre texto, iconos y fondo. Como referencia WCAG 2.1 AA, el texto normal debe alcanzar 4,5:1 y el texto grande 3:1.
- Todas las funciones principales deben poder operarse mediante teclado.
- Foco visible al navegar con teclado y orden de tabulación coherente.
- Etiquetas accesibles en formularios, campos y botones.
- Mensajes de error comprensibles y asociados al campo correspondiente.
- Texto alternativo para imágenes informativas; imágenes decorativas correctamente ignoradas por tecnologías de asistencia.
- Estructura semántica con encabezados, regiones, listas y controles HTML adecuados.
- No transmitir estados solo con color; añadir texto o iconos con significado accesible.
- Ampliación de texto y diseño adaptable a móviles sin pérdida de información ni funcionalidad.
- Pruebas con navegación de teclado y, cuando sea posible, un lector de pantalla además de verificaciones automáticas.
La revisión de accesibilidad se incorporará a las pruebas del MVP, no únicamente a la revisión final de la interfaz.
## 8. Propiedad intelectual y licencias
El código, los diseños, la documentación y otros materiales originales pueden estar protegidos por la normativa de propiedad intelectual. El equipo debe poder justificar que dispone de autorización para utilizar los recursos externos incluidos en el proyecto.
Medidas propuestas:
- Registrar las dependencias de `npm` que se incorporen y revisar sus licencias y condiciones de uso.
- Utilizar imágenes, iconos, fuentes, plantillas y componentes con licencia compatible con el uso previsto.
- Conservar las atribuciones exigidas por las licencias, incluidas las de Creative Commons cuando proceda.
- No copiar código, ilustraciones, fotografías ni contenido comercial de terceros sin autorización.
- Revisar los términos de las APIs y servicios externos integrados.
- Documentar las licencias relevantes en un archivo de terceros, por ejemplo `docs/licencias-terceros.md`, si el número de dependencias o recursos lo justifica.
- Acordar entre los miembros del equipo cómo se atribuye y comparte el trabajo del proyecto académico.
Referencia: [Ley de Propiedad Intelectual - texto consolidado del BOE](https://www.boe.es/eli/es/rdlg/1996/04/12/1/con).
## 9. Normativa sectorial y límites funcionales
### 9.1. Servicios sociales y ayuda a domicilio
La Ley 9/2016 de Servicios Sociales de Andalucía puede resultar relevante para las entidades que desarrollan actividades de servicios sociales en la comunidad autónoma. Las obligaciones específicas pueden depender de si el cliente presta un servicio autorizado, de su relación con la Administración y de las condiciones del contrato o programa correspondiente.
Para CUIDALIA, la medida inicial consiste en confirmar con la entidad cliente qué normativa sectorial debe cumplir y trasladar al software únicamente los requisitos que le correspondan. No se afirma que el proveedor tecnológico tenga automáticamente las mismas obligaciones que la entidad que presta materialmente el servicio.
### 9.2. Medicación e información de salud
La aplicación puede registrar tareas relacionadas con la medicación como parte del servicio de atención domiciliaria. Esto implica tratar información personal de salud, pero no convierte por sí solo a CUIDALIA en un sistema de diagnóstico o prescripción médica.
El alcance del MVP debe permanecer en la coordinación y el registro operativo. Si se ampliara para emitir recomendaciones clínicas, gestionar historias clínicas, prescribir tratamientos o integrarse con sistemas sanitarios, sería necesaria una evaluación jurídica y técnica específica antes de desarrollar esas funciones.
## 10. Plan de implementación técnica
La siguiente tabla convierte la normativa en tareas concretas para el desarrollo. El estado inicial de todas las tareas es **pendiente de implementación o verificación**; no deben presentarse como completadas hasta haberlas probado.
| ID | Requisito | Implementación propuesta | Cómo se verificará | Estado |
|---|---|---|---|---|
| LEG-01 | Informar del tratamiento de datos | Crear `/legal/privacidad` y enlazarla desde el registro y el pie de página. | Revisar que se identifican responsable, finalidades, bases, derechos, destinatarios y conservación. | Pendiente |
| LEG-02 | Informar y recoger aceptación de condiciones | Incorporar una casilla no premarcada para aceptar las condiciones y mostrar el aviso de privacidad. | Comprobar que no se crea la cuenta si falta la aceptación obligatoria y que no se mezcla con consentimiento comercial. | Pendiente |
| LEG-03 | Base jurídica para datos de salud | Documentar la base del artículo 6 y la condición aplicable del artículo 9 para cada finalidad real. | Revisión del responsable del tratamiento antes de introducir datos reales. | Pendiente |
| LEG-04 | Control de acceso | Aplicar roles y comprobar en backend que cada petición está autorizada para la persona y servicio correspondientes. | Pruebas con cuentas de coordinación, trabajador y familiar intentando acceder a datos ajenos. | Pendiente |
| LEG-05 | Contraseñas y comunicaciones | Hash seguro de contraseñas, HTTPS en despliegue y gestión segura de sesiones y secretos. | Revisar configuración y realizar pruebas técnicas antes de producción. | Pendiente |
| LEG-06 | Ejercicio de derechos | Implementar consulta/exportación JSON y un flujo verificable de solicitud de supresión. | Probar exportación, verificación de identidad, registro de la solicitud y conservación legal cuando proceda. | Pendiente |
| LEG-07 | Cookies | Crear `/legal/cookies` y banner con aceptar, rechazar y configurar cuando haya cookies no exentas. | Inspeccionar cookies antes y después del consentimiento y comprobar que las no necesarias no se cargan antes. | Pendiente |
| LEG-08 | Condiciones de uso | Crear `/legal/terminos` adaptada a roles, finalidad, obligaciones del cliente y límites del producto. | Revisar que el texto corresponde al funcionamiento real y enlaza con las otras políticas. | Pendiente |
| LEG-09 | Geolocalización laboral | Informar antes del uso, limitar la ubicación al fichaje y restringir el acceso a los registros. | Verificar el flujo de consentimiento/permisos del dispositivo, momento de captura y permisos de lectura. | Pendiente |
| LEG-10 | Accesibilidad | Seguir WCAG 2.1 AA en contraste, teclado, semántica, formularios e imágenes. | Combinar revisión automática, navegación manual con teclado y comprobación de contraste. | Pendiente |
| LEG-11 | Propiedad intelectual | Auditar licencias de dependencias y recursos visuales. | Mantener inventario de recursos de terceros y enlaces a sus licencias. | Pendiente |
| LEG-12 | Gestión de incidentes | Definir procedimiento para analizar, registrar y escalar brechas de seguridad. | Simular un incidente y comprobar responsables, registro y criterio de notificación. | Pendiente |
| LEG-13 | Evaluación del riesgo | Realizar análisis de riesgos y decidir documentadamente si es necesaria una EIPD y/o un DPD. | Conservar el análisis y la decisión antes de tratar datos reales. | Pendiente |
| LEG-14 | Contrato con encargados | Si CUIDALIA presta software a entidades clientes, preparar contrato de encargo del tratamiento y revisar subencargados. | Verificar que el contrato incluye los elementos del artículo 28 del RGPD. | Pendiente |
| LEG-15 | Registro de jornada | Si el fichaje pretende cubrir la obligación laboral, verificar contenido, conservación y acceso a los registros durante cuatro años. | Contrastar requisitos con la entidad empleadora y probar la exportación o consulta del registro. | Pendiente |
### 10.1. Rutas legales previstas
La aplicación expondrá las páginas legales en las siguientes rutas, tal como establece el criterio de evaluación:
- `/legal/privacidad`
- `/legal/cookies`
- `/legal/terminos`
Las tres rutas deberán ser accesibles desde el registro y desde un pie de página disponible en las pantallas principales. No deberán depender exclusivamente de un enlace escondido en una pantalla secundaria.
## 11. Fuentes oficiales y recursos de consulta
1. [Reglamento (UE) 2016/679 - RGPD, EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj?locale=es)
2. [Ley Orgánica 3/2018 - LOPDGDD, BOE](https://www.boe.es/eli/es/lo/2018/12/05/3/con)
3. [Ley 34/2002 - LSSI-CE, BOE](https://www.boe.es/eli/es/l/2002/07/11/34/con)
4. [AEPD - Guía sobre el uso de las cookies (mayo de 2024)](https://www.aepd.es/es/documento/guia-cookies.pdf)
5. [AEPD - Protección de datos desde el diseño](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/proteccion-de-datos-desde-el-diseno)
6. [AEPD - Evaluación de impacto de protección de datos](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/realizacion-de-evaluaciones-de)
7. [Ley 11/2023 - accesibilidad de determinados productos y servicios, BOE](https://www.boe.es/buscar/act.php?id=BOE-A-2023-11022)
8. [Real Decreto 1112/2018 - accesibilidad del sector público, BOE](https://www.boe.es/eli/es/rd/2018/09/07/1112)
9. [Estatuto de los Trabajadores - texto consolidado, BOE](https://www.boe.es/eli/es/rdlg/2015/10/23/2/con)
10. [Real Decreto-ley 8/2019 - registro de jornada, BOE](https://www.boe.es/eli/es/rdl/2019/03/08/8/con)
11. [Ley 9/2016 de Servicios Sociales de Andalucía, BOE](https://www.boe.es/eli/es-an/l/2016/12/27/9/con)
12. [Ley de Propiedad Intelectual - texto consolidado, BOE](https://www.boe.es/eli/es/rdlg/1996/04/12/1/con)
