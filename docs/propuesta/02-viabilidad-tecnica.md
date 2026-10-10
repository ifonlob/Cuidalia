# Viabilidad técnica

## Introducción

---

## 1. Requisitos funcionales

### 1.1 Funcionalidades principales

### 1.2 Priorización MoSCoW
#### Must have
#### Should have
#### Could have
#### Won't have

### 1.3 MVP (Producto Mínimo Viable)
#### Recorrido mínimo de la user persona
#### Requisitos incluidos en el MVP
#### Qué queda fuera del MVP

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
A continuación, se identifican los principales riesgos que podrían afectar al desarrollo, rendimiento o adopción del sistema:

1. **Problemas de conectividad:** Pérdida de conexión o falta de cobertura de red móvil durante el check-in/check-out y completado de tareas por parte de los cuidadores dentro de los domicilios.
2. **Dependencia de terceros (APIs):** Retrasos o fallos en la integración con servicios de geolocalización o mapas (como OpenRouteService).
3. **Cuellos de botella en el servidor:** Sobrecarga del backend (Node.js) ante picos de avisos masivos, como el envío simultáneo de notificaciones por bajas y sustituciones.
4. **Adopción por parte del usuario:** Resistencia al uso de la aplicación por parte de cuidadores con menor destreza o brecha digital.
5. **Desviación de plazos (Scope creep):** Retrasos en el desarrollo provocados por cambios o ampliación de alcance en los requisitos por parte del equipo de coordinación.

### 4.2 Estrategias de mitigación
Para cada riesgo identificado, se aplicarán las siguientes medidas preventivas antes de que ocurran:

| Riesgo | Estrategia de Mitigación |
| :--- | :--- |
| **Problemas de conectividad** | Implementar almacenamiento local en el frontend (mediante capacidades PWA/Service Workers) para que los fichajes y checklists se guarden temporalmente en el dispositivo y se sincronicen automáticamente con la base de datos al recuperar la cobertura. |
| **Dependencia de APIs de mapas** | Seleccionar APIs estables con SDKs probados y desarrollar una capa de abstracción temprana en el código. Esto nos permitirá cambiar rápidamente a un proveedor alternativo (o usar la fórmula de Haversine nativa) si surgen limitaciones, caídas o costes inesperados. |
| **Sobrecarga del backend** | Utilizar un sistema de colas de mensajes (como Redis o similar) para encolar y procesar las notificaciones push masivas de forma asíncrona. Esto evitará bloqueos en el hilo principal del servidor y asegurará la disponibilidad del sistema. |
| **Resistencia al uso (brecha digital)** | Diseñar una interfaz orientada a móviles extremadamente simplificada, con textos grandes y botones claros. Se complementará realizando sesiones de formación práctica con los cuidadores previas al despliegue oficial. |
| **Desviaciones en los plazos** | Establecer un MVP con alcance cerrado y estricto. Se aplicarán metodologías ágiles con iteraciones cortas para validar tempranamente cada funcionalidad con los coordinadores antes de avanzar, bloqueando la entrada de nuevas peticiones funcionales hasta la siguiente fase. |
