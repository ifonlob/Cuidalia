# Cuidalia - Definición del Problema

## Introducción

## 1. Identificación de la necesidad

### El Problema

### ¿A quién afecta y con qué frecuencia?

### Impacto

### Evidencias


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
