# Fase 3 · Objetivos y alcance · <estudio>
## Introducción
## 1. Objetivos
### Objetivo general

Minimizar el estrés en los cuidados a domicilio, reduciendo el tiempo que coordinadores, cuidadores y familias dedican a gestionar cambios y comunicarse.

### Objetivos específicos

Un coordinador sea capaz de gestionar una baja rápidamente.
Que un familiar tenga toda la información necesaria sin navegar por la web o app.
Que un trabajador sepa lo antes posible si tiene que sustituir una baja.
Que el trabajador pueda marcar una tarea como completada sin afectar de forma significativa a su jornada laboral.

### Medición de los objetivos

Comprobaremos que se puede navegar por la web hasta gestionar la baja realizando menos de 7 clics.
Utilizaremos a un usuario de prueba que nos diga si es capaz de obtener toda la información que necesita saber sobre el servicio sin salir de la página principal.
Analizaremos el flujo de usuario desde que entra a la app hasta que marca una tarea como completada y nos aseguraremos de que tarda menos de 15 segundos.

## 2. Alcance

### El MVP
[Enlace al MVP (userflows)](https://github.com/ifonlob/Cuidalia/blob/a1246e09338fdd3d17da7e887e8a6f1102501bd4/docs/propuesta/02-viabilidad-tecnica.md?plain=1#L206-L238)

[Enlace Resumen MVP](https://github.com/ifonlob/Cuidalia/blob/fd10b7cf92ab23686cafc0e89e459a84f32c1cd6/docs/propuesta/02-viabilidad-tecnica.md?plain=1#L250-L258)

### Plataforma

La aplicación se desarrollará con una arquitectura web adaptativa (PWA), dividiendo el acceso según las necesidades de cada rol:
*   **Escritorio (Web):** Acceso exclusivo para el perfil de **Coordinador**. Estará optimizado para pantallas grandes, lo que permite visualizar cuadrantes completos, aplicar filtros complejos y gestionar múltiples perfiles de forma eficiente.
*   **Móvil (Web App / PWA):** Acceso principal para el **Cuidador** y el **Familiar**. Su interfaz estará diseñada para un uso ágil desde el teléfono, priorizando el y marcaje de tareas realizadas de forma eficiente, la recepción de notificaciones inmediatas y la consulta del resumen diario en pocos toques.

### Usuarios y datos

Para el desarrollo, testeo y demostración final del MVP, se utilizará un entorno recortado y seguro:
*   **Cantidad de usuarios:** Un volumen reducido de prueba que incluya 2-3 coordinadores, unos 10 cuidadores y 10-15 familiares.
*   **Origen y tipo de datos:** Se utilizarán exclusivamente **datos de prueba mock inventados**. No se utilizará información real bajo ningún concepto para cumplir de forma estricta con la normativa de protección de datos (RGPD), dado que el sistema maneja información de salud. 
*   **Ubicación:** Las direcciones y rutas simuladas se centrarán en la zona de San Fernando y alrededores para probar el cálculo de distancias (OpenRouteService/Haversine) de forma coherente en un mismo entorno local.

### Lo que no haremos

| Qué | Por qué |
| :--- | :--- |
| **Generación automática/IA de cuadrantes** | El objetivo principal del MVP es gestionar imprevistos (bajas y sustituciones). Crear un algoritmo complejo de planificación mensual desde cero consumiría casi todo el tiempo de desarrollo. |
| **Pasarelas de pago y facturación** | Implica una gran complejidad legal y técnica (seguridad bancaria, normativas) que desvía el foco del problema central: la comunicación, el tiempo y las tareas de cuidado. |
| **Integración con la sanidad pública** | Conectarse al historial clínico de la comunidad autónoma requiere convenios institucionales y APIs cerradas que están totalmente fuera del alcance del proyecto. |

### Ampliaciones futuras

Si dispusiéramos de más tiempo de desarrollo, estas serían las siguientes funcionalidades a implementar, ordenadas por prioridad de valor aportado:

1. **Mensajería interna (Chat centralizado):** Integrar un chat dentro de la plataforma para coordinadores, familiares y cuidadores, con el fin de eliminar definitivamente la dependencia de llamadas telefónicas y grupos de WhatsApp dispersos.
2. **Botón de emergencia (SOS):** Añadir un acceso directo e intuitivo en la vista del cuidador para notificar una urgencia de salud, alertando a la vez a la oficina y a la familia, y mostrando los números de emergencia relevantes.
3. **Solicitudes directas de la familia:** Implementar un sistema de tickets o formularios donde el familiar pueda pedir adelantar una hora de servicio o añadir una tarea puntual (ej. una nueva crema), con seguimiento de si ha sido aprobada o no.
4. **Generador de informes para nóminas:** Aprovechar la base de datos de fichajes y sustituciones para calcular automáticamente el total de horas mensuales trabajadas por cada empleado y permitir su exportación (CSV/PDF) para el departamento laboral.
