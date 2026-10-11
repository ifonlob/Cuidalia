# Viabilidad técnica

## Introducción

---

## 1. Requisitos funcionales

## 1. Persona principal: Coordinador/a

### Gestionar el cuadrante de horarios
El coordinador crea y modifica los horarios de usuarios y trabajadores desde una vista que muestra disponibilidades, vacaciones y huecos libres. Así deja de rehacer cuadrantes enormes en Excel cada vez que hay un cambio.

### Asignar un trabajador a un usuario
El coordinador busca al cuidador adecuado con filtros de compatibilidad:

- Fuerza para usar grúa.
- Experiencia en demencias.
- Alergias a mascotas.
- Baño adaptado.
- Carácter.
- Distancia al domicilio.

Esto reduce los emparejamientos fallidos, que obligan a empezar de cero.

### Gestionar el perfil del usuario
El coordinador registra y actualiza la siguiente información:

- Grado de dependencia.
- Necesidad de aseo en cama.
- Medicación.
- Horario contratado.
- Contactos de la familia.

Toda esa información queda en un único lugar, en vez de repartida entre papel, Excel y WhatsApp.

### Gestionar bajas y sustituciones
Cuando un trabajador no puede acudir, el coordinador envía un aviso a varios cuidadores disponibles a la vez y el primero que acepta desde la app se queda con el servicio.

Se evita llamar uno por uno a quienes libraban.

### Notificar cambios a familia y cuidadores
El sistema avisa automáticamente de los cambios de horario o de trabajador. El coordinador deja de hacer de «centralita».

### Monitorizar las visitas en tiempo real
El coordinador ve quién ha llegado, quién se retrasa y quién no se ha presentado, y recibe alertas.

Así detecta los fallos antes de que la familia llame para quejarse.

### Gestionar incidencias
El coordinador registra, prioriza y hace seguimiento de las incidencias, como:

- Bajas.
- Síntomas extraños.
- Cambios por citas médicas.
- Malas noches.

Todas quedan documentadas y no solo comunicadas por teléfono.

### Consultar ubicación y huecos de los trabajadores
El coordinador ve dónde está cada trabajador y qué huecos reales tiene, sin revisar el Excel celda por celda.

### Generar el informe de horas para nóminas
El sistema calcula las horas trabajadas y las sustituciones del mes.

Desaparecen los post-its y los colores en Excel.

### Revisar el historial de tareas
El coordinador consulta lo realizado en cada visita, con seguimiento diario y no solo la hoja de firmas mensual.

### Comunicarse por mensajería interna
El coordinador se comunica con familias y cuidadores desde un canal único, sin líneas saturadas ni WhatsApps dispersos.

---

## 2. Persona secundaria 1: Familiar

### Consultar el resumen diario de tareas
El familiar abre la app y ve de un vistazo:

- Medicación.
- Comida.
- Aseo.
- Cómo ha dormido su familiar.
- Su estado de ánimo.

Así no tiene que llamar a la oficina ni esperar a la tarde para saberlo.

### Recibir alertas inmediatas
Ante un mareo, una caída u otro evento grave, el familiar recibe una notificación destacada en el móvil.

### Solicitar cambios o necesidades
El familiar pide, por ejemplo, adelantar la visita por una cita médica o aplicar una crema en la pierna derecha, y ve el estado de la solicitud.

Evita las esperas de dos horas y la pérdida de detalles por el «teléfono escacharrado».

### Conocer al cuidador sustituto
El familiar recibe un aviso anticipado del cambio y puede ver el nombre, la foto, la experiencia y la formación de la persona nueva.

Así no se entera por su padre de que ha venido alguien desconocido.

### Chatear con coordinación o con el cuidador
El familiar tiene un canal directo y transparente, sin sentir que molesta.

### Consultar el calendario de visitas
El familiar sabe quién va a ir y cuándo.

### Usar la app cómodamente desde el móvil
La interfaz es visual, con pocos menús y sesión persistente, porque el familiar dispone de poco tiempo.

---

## 3. Persona secundaria 2: Cuidador/a

### Consultar la agenda personal
El cuidador ve sus servicios, direcciones y horarios, y recibe los cambios en tiempo real.

Sustituye al cuadrante en papel o a la foto de WhatsApp.

### Avisar de que no puede acudir
El cuidador pulsa un botón de baja y el sistema avisa a coordinación automáticamente.

Se acaban las llamadas a una oficina saturada.

### Ver el perfil del usuario
El cuidador consulta la siguiente información antes de la visita, sobre todo en las primeras:

- Movilidad.
- Patologías.
- Alergias.
- Mascotas.
- Medicación.
- Dieta.

### Consultar notas y rutinas del usuario
El cuidador ve las manías del usuario, la rutina del cuidador titular y dónde están los objetos clave.

Es especialmente útil en las sustituciones.

### Registrar llegada y salida
El cuidador hace *check-in* y *check-out*, con geolocalización.

Esto le protege ante reclamaciones y justifica el tiempo real en el domicilio.

### Marcar las tareas realizadas
El cuidador completa un *checklist* detallado con medicación a su hora, comida, aseo y cremas, en lugar de la hoja de papel y de tareas genéricas.

### Reportar incidencias
El cuidador registra situaciones como:

- Negativas a medicarse.
- Caídas.
- Falta de material.
- Peticiones fuera del plan.

Así no depende de una llamada.

### Activar un botón de emergencia
El cuidador avisa a coordinación y a la familia a la vez, y tiene a mano los contactos que necesita en una urgencia.

### Recibir avisos de cambios importantes
El cuidador es informado de cambios en medicación, movilidad o citas, con confirmación de lectura.

---

## 4. Priorización de funcionalidades

### 4.1. Must have

Funcionalidades imprescindibles para la primera versión del producto:

- **Autenticación y roles:** sin permisos diferenciados, la familia vería datos que no debe.
- **Cuadrante:** crear y editar servicios manualmente.
- **Perfil del usuario:** dependencia, medicación, horario contratado y contactos de la familia.
- **Bajas y sustituciones:** aviso a los candidatos y aceptación desde la app.
- **Notificaciones de cambios:** a familia y cuidadores.
- **Monitorización de visitas:** quién ha llegado, quién se retrasa y quién no ha aparecido.
- **Perfil del cuidador.**
- **Perfil del usuario visible para el cuidador.**
- **Check-in y check-out.**
- **Checklist de tareas realizadas.**

### 4.2. Should have

Funcionalidades importantes que pueden incorporarse después de las imprescindibles:

- **Incidencias:** el coordinador las gestiona y el cuidador las reporta.
- **Historial de tareas consultable.**
- **Alertas inmediatas de eventos graves.**
- **Solicitudes de la familia:** por ejemplo, adelantar una visita.

---

## 5. Producto Mínimo Viable (MVP)

### 5.1. Coordinador/a: recorrido mínimo para gestionar una baja

**Objetivo:** permitir que el coordinador encuentre una sustitución para un servicio afectado por la baja de un trabajador.

1. En la pestaña principal, toca el apartado **«Cuadrantes»**.
2. Una vez dentro, filtra por el trabajador que se ha dado de baja.
3. Selecciona el turno afectado.
4. Pulsa el botón **«Asignar sustitución»**.
5. En el *pop-up* de **«Detalles del turno»**, elige a un trabajador disponible.
6. Pulsa el botón **«Asignar turno»**.
7. El trabajador acepta el turno en su app.

### 5.2. Familiar: recorrido mínimo para asegurarse de que todo ha ido bien

**Objetivo:** permitir que el familiar compruebe que el servicio ha finalizado y que las tareas se han realizado correctamente.

1. El familiar entra en la aplicación mediante una notificación que avisa sobre el fin del trabajo.
2. Comprueba que la sesión no ha caducado.
3. Entra en el **«Resumen del día»**.
4. Revisa que las tareas hayan ido bien.
5. Cierra la aplicación y mantiene la calma.

### 5.3. Cuidador/a: recorrido mínimo para completar un servicio sin incidencias

**Objetivo:** permitir que el cuidador registre su llegada, complete las tareas asignadas y guarde el resultado del servicio.

1. El trabajador llega a la puerta de la casa del usuario, abre la app y la aplicación verifica si hay cobertura en el interior.
2. El trabajador accede a la pantalla **«Mis turnos hoy»** y selecciona el turno actual.
3. Dentro de la **«Ficha del servicio actual»**, pulsa el botón **«Fichar entrada»**. El sistema registra la hora de entrada y el trabajador pulsa **«Ver tareas»**.
4. Se muestra el **«Checklist de tareas específicas»**. Al no surgir ninguna anomalía durante el servicio, el trabajador simplemente va marcando los checks de las tareas completadas.
5. Como no ha dejado tareas obligatorias sin marcar, el sistema valida la información automáticamente. Se genera el mensaje **«Resumen del servicio guardado con éxito y sincronizado»**, tras lo cual el trabajador cierra la aplicación y se desplaza a la siguiente casa.

---

## 6. Resumen de los perfiles y sus objetivos

| Perfil | Objetivo principal |
|---|---|
| **Coordinador/a** | Gestionar horarios, asignaciones, sustituciones e incidencias desde un único lugar. |
| **Familiar** | Consultar el estado de su familiar, conocer las visitas y comunicarse con coordinación. |
| **Cuidador/a** | Consultar sus servicios, registrar la jornada, completar tareas y comunicar incidencias. |

## 7. Resumen del alcance del MVP

El MVP se centra en tres recorridos esenciales:

1. **Coordinación:** gestionar una baja y asignar una sustitución.
2. **Familiar:** consultar el resumen diario tras finalizar el servicio.
3. **Cuidador/a:** fichar la entrada, completar las tareas y guardar el servicio.

Estos recorridos permiten validar el funcionamiento básico de la gestión de servicios, la comunicación entre perfiles y el seguimiento de las visitas.


---

## 2. Requisitos técnicos

### 2.1 Frontend (React)
#### Navegación
#### Gestión del estado
#### Componentes de interfaz
#### Peticiones al backend
#### Otras bibliotecas

### 2.2 Backend (Node.js + Express)
#### Autenticación
#### Roles y permisos
#### APIs y servicios externos

### 2.3 Base de datos (MongoDB)
#### Colecciones principales
#### Campos de cada colección
#### Relaciones entre colecciones
#### Diagrama del esquema

### 2.4 Infraestructura
#### Despliegue del frontend
#### Despliegue del backend
#### Despliegue de la base de datos
#### Servicios cloud y condiciones del plan gratuito

---

## 3. Capacidades del equipo

### 3.1 Inventario de habilidades

### 3.2 Lagunas de conocimiento

### 3.3 Viabilidad en el tiempo disponible
#### Valoración
#### Recortes del MVP (si son necesarios)

---

## 4. Riesgos técnicos
### 4.1 Listado de riesgos

### 4.2 Estrategias de mitigación
