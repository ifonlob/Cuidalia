# Fase 3 · Objetivos y alcance · Estudio

## Introducción

CUIDALIA busca reducir el estrés asociado a la coordinación de los servicios de ayuda a domicilio, facilitando la gestión de bajas y sustituciones y mejorando la comunicación entre coordinación, trabajadores y familias. El MVP se centrará en un recorrido principal: localizar un servicio afectado por una baja, consultar trabajadores disponibles, asignar un sustituto y comprobar que acepta el turno. Las funciones dirigidas a familiares, el registro de tareas, las notificaciones y las herramientas de geolocalización se plantean como ampliaciones posteriores. El proyecto se desarrollará con datos ficticios y un alcance limitado para poder implementar y probar el recorrido principal dentro del tiempo disponible.

## 1. Objetivos

### Objetivo general

Minimizar el estrés en los cuidados a domicilio, reduciendo el tiempo que coordinadores, cuidadores y familias dedican a gestionar cambios y comunicarse.

### Objetivos específicos

| ID | Objetivo SMART | Qué se mide | Valor de éxito | Cómo se comprueba |
|---|---|---|---|---|
| OE-01 | Antes de la defensa final, permitir que una persona coordinadora localice un servicio afectado por una baja y asigne un sustituto válido en el MVP. | Número de acciones principales y tiempo necesario para completar la identificación y asignación. | Completar el proceso en un máximo de 7 clics y 3 minutos en, al menos, 4 de 5 escenarios de prueba. | Realizar cinco pruebas con datos ficticios, registrar los clics y medir el tiempo desde el acceso a la aplicación hasta la asignación. |
| OE-02 | Antes de la defensa final, permitir que el trabajador consulte y acepte una propuesta de sustitución desde su interfaz. | Tiempo que tarda el trabajador en localizar y aceptar la propuesta. | Aceptar la sustitución en menos de 1 minuto en, al menos, 4 de 5 pruebas. | Ejecutar cinco pruebas del recorrido del trabajador y cronometrar cada una. |
| OE-03 | En una iteración posterior al MVP, permitir que un familiar autorizado consulte la información principal de un servicio desde la página principal, sin tener que navegar por varias secciones. | Capacidad para localizar la información relevante desde la página principal. | Que, al menos, 4 de 5 personas de prueba encuentren la información solicitada sin salir de la página principal. | Plantear tareas de consulta a usuarios de prueba y registrar si encuentran la información correctamente. |
| OE-04 | En una iteración posterior al MVP, permitir que el trabajador marque una tarea del servicio como completada de forma rápida. | Tiempo empleado desde que abre la tarea hasta que la marca como completada. | Completar la acción en menos de 15 segundos en, al menos, 4 de 5 pruebas. | Simular cinco registros de tareas y cronometrar el proceso. |

Los valores indicados son objetivos de evaluación previstos, no resultados ya obtenidos. Los objetivos OE-03 y OE-04 se mantienen como metas para futuras iteraciones, ya que el portal familiar y el registro de tareas no forman parte del MVP descrito en la Fase 2.

## 2. Alcance

### El MVP

El MVP se limita a gestionar una baja y completar una sustitución: la persona coordinadora inicia sesión, localiza un servicio afectado, consulta candidatos disponibles, selecciona un trabajador y confirma la propuesta; después, el trabajador consulta la sustitución y la acepta, y el sistema actualiza su estado.

- [Enlace al MVP (userflows)](https://github.com/ifonlob/Cuidalia/blob/a1246e09338fdd3d17da7e887e8a6f1102501bd4/docs/propuesta/02-viabilidad-tecnica.md?plain=1#L206-L238)
- [Enlace al resumen del MVP](https://github.com/ifonlob/Cuidalia/blob/fd10b7cf92ab23686cafc0e89e459a84f32c1cd6/docs/propuesta/02-viabilidad-tecnica.md?plain=1#L250-L258)

El recorrido principal utilizará datos de prueba ya registrados. En esta versión, la persona coordinadora elegirá un trabajador de la lista de candidatos válidos; no se enviarán avisos simultáneos a varios trabajadores ni se asignará automáticamente el servicio a la primera persona que lo acepte.

### Plataforma

La aplicación se desarrollará como una web adaptativa, con interfaces ajustadas a las necesidades de cada perfil. La instalación como PWA y las notificaciones push se valorarán en una iteración posterior, ya que no son necesarias para completar el MVP.

- **Escritorio (web):** orientado al perfil de coordinación, para consultar los cuadrantes, filtrar los servicios afectados por una baja y asignar un trabajador sustituto.
- **Móvil (web adaptativa):** orientado principalmente al trabajador, para consultar y aceptar la sustitución. En versiones posteriores se podrá ampliar con el registro de tareas y una interfaz para familiares.
- **PWA y notificaciones:** quedan fuera del núcleo del MVP y se estudiarán si hay tiempo después de completar y probar el recorrido de sustitución.

### Usuarios y datos

Para el desarrollo, las pruebas y la demostración final se utilizará un entorno reducido con datos ficticios:

- **Cantidad de usuarios:** se prevé disponer de 2-3 cuentas de coordinación y alrededor de 10 cuentas de trabajadores para las pruebas del MVP. Se pueden preparar también 10-15 perfiles de familiares de prueba para validar futuras iteraciones, pero no tendrán un recorrido funcional obligatorio en esta versión.
- **Origen y tipo de datos:** se utilizarán exclusivamente datos de prueba inventados. No se empleará información personal o sanitaria real durante el desarrollo ni en la demostración.
- **Ubicación:** si se incorporan pruebas de mapas en una iteración posterior, las direcciones simuladas podrán situarse en San Fernando y alrededores. El cálculo de distancias mediante OpenRouteService o Haversine no forma parte del MVP.

### Lo que no haremos

| Qué | Por qué |
|---|---|
| **Generación automática o mediante IA de cuadrantes** | El objetivo principal del MVP es gestionar imprevistos, como bajas y sustituciones. Crear un algoritmo complejo de planificación mensual consumiría demasiado tiempo y ampliaría el alcance. |
| **Pasarelas de pago y facturación** | Implican complejidad técnica y requisitos adicionales de seguridad que desvían el esfuerzo del problema principal: gestionar sustituciones de forma fiable. |
| **Integración con la sanidad pública** | La conexión con historiales clínicos requiere acuerdos, sistemas y requisitos que quedan fuera del alcance del proyecto académico. |
| **PWA, notificaciones push, geolocalización y cálculo de rutas en el MVP** | No son imprescindibles para demostrar el recorrido principal y añadirían trabajo de integración y pruebas. Podrán valorarse después de completar el MVP. |
| **Portal completo para familiares y registro de tareas en el MVP** | Aunque forman parte de la visión general de CUIDALIA, no son necesarios para demostrar la gestión de una baja y la aceptación de una sustitución. |

### Ampliaciones futuras

Si se dispusiera de más tiempo de desarrollo, estas serían las siguientes funcionalidades, ordenadas por la prioridad planteada inicialmente:

1. **Mensajería interna (chat centralizado):** integrar un chat para coordinación, familiares y trabajadores, reduciendo la dependencia de llamadas telefónicas y conversaciones dispersas en otras aplicaciones.
2. **Botón de emergencia (SOS):** añadir un acceso directo en la interfaz del trabajador para facilitar el aviso a coordinación y mostrar teléfonos de emergencia relevantes. No sustituirá a los servicios de emergencia.
3. **Solicitudes directas de la familia:** permitir que los familiares autorizados soliciten cambios de horario o tareas puntuales y consulten el estado de cada solicitud.
4. **Generador de informes para nóminas:** aprovechar los registros de fichajes y sustituciones para calcular las horas mensuales de cada trabajador y permitir su exportación a CSV o PDF para revisión administrativa.
5. **Portal familiar y resumen del servicio:** permitir que los familiares autorizados consulten la información disponible del servicio, así como el registro de tareas cuando esa funcionalidad se haya desarrollado.
6. **Registro de tareas y PWA:** facilitar que el trabajador marque tareas completadas desde el móvil y valorar la instalación de la aplicación y las notificaciones push.
7. **Mapas y apoyo a la selección de sustitutos:** estudiar la integración de OpenRouteService o una estimación Haversine para comparar distancias o tiempos de desplazamiento, sin convertirla en una dependencia del recorrido principal.
