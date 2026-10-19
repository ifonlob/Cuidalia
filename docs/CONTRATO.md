# Contrato de equipo - CUIDALIA

## Compromisos

- **Dedicación semanal:** Cada integrante se compromete a dedicar un mínimo de 2 horas semanales al proyecto fuera del horario lectivo, además del trabajo realizado en clase. Si no alcanza la dedicación acordada, deberá reorganizar su planificación y recuperar el trabajo pendiente durante la semana siguiente, siempre que sea viable.

- **Responsabilidad individual:** Cada miembro será responsable de las tareas que tenga asignadas, respetando los plazos acordados y manteniendo informado al equipo sobre su progreso. Si prevé que no podrá cumplir una entrega, deberá comunicarlo con antelación para reorganizar el trabajo.

- **Incumplimiento reiterado:** Si un integrante no dedica tiempo al proyecto durante dos semanas consecutivas y no existe una causa justificada comunicada al equipo, se tratará la situación internamente y, si no se alcanza un acuerdo, se informará al profesor para buscar una solución.

- **Reuniones semanales:** Se celebrará una reunión obligatoria semanal para revisar el estado del proyecto, comprobar las tareas completadas, identificar bloqueos y planificar el trabajo siguiente. Si algún integrante no puede asistir, deberá avisar con antelación y consultar posteriormente los acuerdos y tareas asignadas.

- **Gestión de bloqueos:** Ningún bloqueo deberá permanecer sin comunicar durante más de 8 horas desde que se detecte. El integrante afectado deberá exponer el problema, indicar qué ha intentado para resolverlo y solicitar ayuda cuando sea necesario. El plazo se refiere a la comunicación y búsqueda de una solución, no garantiza que todos los problemas puedan resolverse en ese tiempo.

- **Seguimiento del trabajo:** Las tareas se organizarán mediante el sistema de seguimiento acordado por el equipo, procurando que cada una tenga un responsable, un objetivo claro y un estado actualizado. Los cambios importantes de alcance o de planificación deberán comunicarse al resto del grupo.

## Comunicación

- **Canal principal:** Discord será el medio principal de comunicación del equipo. El servidor dispondrá de canales específicos para cada finalidad, como `#bloqueos`, `#reuniones`, `#dudas` y `#errores`, con el objetivo de mantener la información organizada y facilitar su consulta.

- **Tiempo de respuesta:** Los integrantes se comprometen a responder a los mensajes del proyecto lo antes posible, procurando hacerlo en un plazo máximo de una hora cuando estén disponibles. Este compromiso no implica disponibilidad permanente ni exige responder durante las horas de descanso, clase u otras obligaciones. Si un mensaje requiere una investigación más larga, bastará con confirmar su recepción e indicar cuándo se podrá responder.

- **Comunicación de bloqueos:** Los problemas que impidan avanzar en una tarea deberán comunicarse directamente en `#bloqueos`, explicando el contexto, el comportamiento esperado, el error encontrado y las posibles soluciones que ya se hayan probado. Cuando sea necesario, se podrá solicitar una reunión breve para resolverlos conjuntamente.

- **Comunicación de errores:** Los errores detectados durante el desarrollo o las pruebas se registrarán en `#errores` o en el sistema de incidencias acordado. Se incluirá, siempre que sea posible, una descripción del problema, los pasos para reproducirlo y su impacto sobre otras funcionalidades.

- **Acuerdos y decisiones:** Las decisiones relevantes sobre arquitectura, tecnologías, funcionalidades, plazos o cambios de alcance deberán quedar registradas en un lugar accesible para todo el equipo, evitando que acuerdos importantes dependan exclusivamente de conversaciones informales.

- **Respeto y claridad:** La comunicación se mantendrá en un tono respetuoso, constructivo y profesional. Las críticas se dirigirán al trabajo, al código o al proceso, nunca a la persona.

## Decisiones y conflictos

- **Toma de decisiones:** Siempre que sea posible, las decisiones se tomarán por consenso, valorando las propuestas de todos los integrantes y priorizando los objetivos, la viabilidad técnica y los requisitos del proyecto.

- **Desacuerdos técnicos:** Cuando existan distintas alternativas, se compararán sus ventajas, inconvenientes, complejidad y consecuencias para el mantenimiento del proyecto. La decisión y sus motivos quedarán documentados para facilitar su revisión posterior.

- **Resolución de conflictos:** Los conflictos deberán abordarse de forma temprana, respetuosa y constructiva. Se dará a cada persona la oportunidad de explicar su punto de vista y se buscará una solución equilibrada que permita continuar el trabajo.

- **Falta de participación:** Si un integrante no cumple reiteradamente sus responsabilidades o no contribuye al trabajo acordado, se hablará primero con él para identificar las causas y establecer compromisos concretos de mejora. Si la situación persiste, el equipo podrá redistribuir las tareas y recurrir al profesor para mediar.

- **Cambios en las responsabilidades:** Cualquier redistribución significativa de tareas deberá comunicarse al equipo, indicando quién asume cada responsabilidad y qué plazos se modifican. Se evitará que una tarea crítica quede sin responsable.

- **Escalado de problemas:** Si no se alcanza una solución mediante el diálogo, se solicitará la intervención del profesor antes de que el conflicto afecte gravemente a la planificación o a la entrega del proyecto.

## Calidad

### Documentación y código generado mediante IA

Todo el código deberá ser comprensible, mantenible y coherente con la arquitectura del proyecto. El código generado o asistido por inteligencia artificial, así como la lógica compleja, deberá revisarse, probarse y documentarse cuando sea necesario para facilitar su comprensión y mantenimiento.

Cada integrante será responsable del código que incorpore al repositorio, independientemente de si lo ha escrito manualmente o con ayuda de herramientas de IA. Ningún fragmento se integrará sin que su autor comprenda su funcionamiento y pueda justificar las decisiones técnicas adoptadas.

### Garantía de funcionamiento

Antes de proponer la integración de cambios, el desarrollador deberá comprobar que la funcionalidad implementada funciona según los requisitos establecidos y que no rompe comportamientos existentes.

Las pruebas deberán ser proporcionales al cambio realizado e incluir, cuando corresponda, pruebas manuales, pruebas automatizadas y comprobaciones de integración. Los errores conocidos que no puedan resolverse antes de la integración deberán comunicarse y documentarse.

### Flujo de Pull Requests (PR)

- **Protección de ramas:** Quedan prohibidos los commits directos a `main`. La integración del trabajo se realizará mediante Pull Requests (PR), siguiendo el flujo de ramas acordado por el equipo.

- **Revisión obligatoria:** Todas las PR deberán ser revisadas y aprobadas por Irene antes de integrarse, de acuerdo con la responsabilidad de revisión establecida por el equipo. La revisión comprobará la corrección del código, su legibilidad, el cumplimiento de los requisitos y los posibles efectos sobre otras funcionalidades.

- **Calidad de las PR:** Cada PR deberá centrarse en un cambio concreto, incluir una descripción clara de su objetivo y evitar archivos innecesarios, código de depuración, comentarios obsoletos o modificaciones ajenas a la tarea.

- **Resolución de observaciones:** El autor de la PR deberá atender las observaciones de revisión y realizar las modificaciones necesarias antes de solicitar la aprobación definitiva.

- **Trazabilidad:** Siempre que sea posible, las PR estarán vinculadas a una tarea o incidencia del proyecto, facilitando el seguimiento de los requisitos y de las decisiones tomadas.

- **Revisión por el equipo:** Aunque Irene sea la responsable de la aprobación obligatoria, se fomentará que todos los integrantes participen en las revisiones para distribuir el conocimiento y evitar que una sola persona sea la única que comprenda partes importantes del sistema.

### Estándares y limpieza del código

Todo el código deberá seguir unas convenciones comunes de nomenclatura, estructura y formato. Se utilizarán nombres descriptivos para variables, funciones, clases, componentes y archivos, evitando abreviaturas confusas y duplicación innecesaria.

Se emplearán herramientas de formateo y análisis estático compatibles con el stack del proyecto para mantener un estilo uniforme. Los cambios deberán respetar la arquitectura y las convenciones establecidas, evitando introducir dependencias o complejidad innecesarias.

### Mantenimiento del repositorio y documentación

El repositorio deberá mantenerse organizado y actualizado. Si un cambio incorpora nuevas dependencias, modifica los comandos de instalación, altera la configuración o cambia el procedimiento de ejecución, el responsable deberá actualizar el `README.md` o la documentación técnica correspondiente.

Las instrucciones deberán permitir que otro integrante pueda configurar y ejecutar el proyecto siguiendo los pasos documentados, sin depender de explicaciones privadas del autor.

Las decisiones técnicas relevantes, los cambios de configuración y las limitaciones conocidas deberán quedar documentados cuando afecten al resto del equipo.

### Seguridad

Queda estrictamente prohibido subir al repositorio credenciales, contraseñas, claves de API, tokens de acceso o cualquier otro secreto.

Las variables sensibles deberán gestionarse mediante variables de entorno, utilizando archivos `.env` excluidos del control de versiones y proporcionando, cuando sea necesario, un archivo de ejemplo como `.env.example` sin valores reales.

Cada integrante deberá comprobar los archivos que va a subir antes de realizar un commit. Si se expone accidentalmente una credencial, deberá comunicarse inmediatamente al equipo, revocarse o sustituirse y eliminarse de la forma adecuada del historial cuando proceda. Borrar el archivo en un commit posterior no será suficiente para considerar resuelto el incidente.

### Protección de datos

Dado que CUIDALIA está orientada a la atención domiciliaria y podría gestionar información personal y datos de salud, el desarrollo deberá priorizar la privacidad y el control de acceso desde el diseño.

Durante las pruebas académicas se utilizarán datos ficticios o debidamente anonimizados. No se incorporará información real de personas atendidas al repositorio ni a entornos de prueba sin la autorización y las garantías que correspondan.

Los permisos deberán limitar el acceso a la información según el rol y las funciones de cada usuario. Asimismo, se evitará almacenar datos personales que no sean necesarios para los objetivos del proyecto.

### Revisión y cumplimiento del contrato

Todos los integrantes se comprometen a conocer y respetar las normas recogidas en este documento. Si una norma deja de ser adecuada o resulta necesario modificarla, el equipo revisará el cambio conjuntamente y registrará la nueva versión para que todos conozcan los acuerdos vigentes.
