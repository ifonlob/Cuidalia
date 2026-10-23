# Fase 4 · Recursos · Cuidalia Studio

## Introducción

En esta fase se definen los recursos humanos, tecnológicos y organizativos necesarios para llevar a cabo el desarrollo del MVP de **Cuidalia**, estableciendo los roles técnicos de cada integrante, la asignación de responsabilidades por módulo funcional, el stack tecnológico y la metodología de trabajo en equipo.

## 1. Las personas

### Roles técnicos

| Persona | Rol | De qué responde |
| :--- | :--- | :--- |
| **Daniel Espinosa** | Frontend | Arquitectura del cliente en React, maquetación responsive/PWA con Tailwind CSS, enrutamiento protegido por rol (`React Router`) e integración con la API. |
| **Irene Foncubierta** | Backend | Arquitectura del servidor en Node.js y Express, lógica de negocio, autenticación JWT, seguridad (middlewares, CORS, bcrypt) e integración con OpenRouteService. |
| **Pablo Reyes** | Database | Modelado de esquemas y validaciones en Mongoose, administración del clúster en MongoDB Atlas, relaciones entre colecciones y datos de prueba (seed/mocks). |
| **Alejandro Espinosa** | QA | Aseguramiento de la calidad, diseño y ejecución de pruebas unitarias e integración (Vitest, Jest y Supertest), validación de flujos del MVP y revisión de estándares de código. |

### Responsables por módulo

| Módulo | Requisitos (RF) | Responsable | Apoyo |
| :--- | :--- | :--- | :--- |
| **Módulo 1: Autenticación y Accesos** | Login seguro con credenciales, generación de tokens (JWT), persistencia de la sesión y redirección a la interfaz correspondiente según el rol.<br>• [RF Must Have: Autenticación y sesión (L172)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L172)<br>• [Requisitos técnicos: Autenticación y roles (L278-L283)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L278-L283) | **Daniel Espinosa** | **Irene Foncubierta** |
| **Módulo 2: Cuadrante y Sustituciones** | Visualización de turnos, filtrado por baja, pop-up de asignación de sustitutos y lógica de aceptación de turno en la app del trabajador.<br>• [RF Must Have: Cuadrante y sustituciones (L173-L174)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L173-L174)<br>• [RF Coordinador: Cuadrante y bajas (L12-L42)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L12-L42)<br>• [MVP 5.1: Recorrido Coordinador (L208-L219)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L208-L219) | **Irene Foncubierta** | **Alejandro Espinosa** |
| **Módulo 3: Ejecución del Servicio** | Pantalla de "Mis turnos hoy", sistema de fichaje geolocalizado con tolerancia offline y el checklist de tareas interactivas.<br>• [RF Must Have: Fichaje y checklist (L175-L176)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L175-L176)<br>• [RF Cuidador: Llegada, salida y tareas (L141-L148)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L141-L148)<br>• [MVP 5.3: Recorrido Cuidador (L230-L239)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L230-L239) | **Alejandro Espinosa** | **Pablo Reyes** |
| **Módulo 4: Resumen y Notificaciones** | Validación automática de tareas, generación del reporte diario, envío de notificación push de finalización y vista del "Resumen del día".<br>• [RF Must Have: Resumen diario automatizado (L177)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L177)<br>• [RF Familiar: Resumen diario y alertas (L79-L92)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L79-L92)<br>• [MVP 5.2: Recorrido Familiar (L220-L229)](https://github.com/ifonlob/Cuidalia/blob/d5e0ba8029531bc7946125b204580bf486ab0d74/docs/propuesta/02-viabilidad-tecnica.md#L220-L229) | **Pablo Reyes** | **Daniel Espinosa** |

### Comunicación

Las normas de convivencia, toma de decisiones, canales de comunicación (WhatsApp para avisos rápidos, Discord para reuniones de seguimiento y GitHub para revisiones de código y gestión de tareas) quedan recogidas en el contrato del equipo:

- **Enlace al contrato de equipo:** [Contrato de equipo (`docs/CONTRATO.md`)](../CONTRATO.md)
    
## 2. La tecnología

### Stack, servicios y APIs

La arquitectura del sistema, el desglose de librerías con su justificación técnica y los límites operativos de los servicios gratuitos se encuentran detallados en la fase previa:

- **Enlace permalink a la viabilidad técnica:** [Fase 2 · Viabilidad técnica (Stack, servicios y APIs: L262-L309)](https://github.com/ifonlob/Cuidalia/blob/027d2283a9534456efeb7c926bc77fd4d8b117a8/docs/propuesta/02-viabilidad-tecnica.md#L262-L309)

#### Justificación del stack y corrección de feedback (A0.4)
Siguiendo las observaciones del feedback recibido, se ha especificado el por qué de cada tecnología y las restricciones de uso gratuito:

- **Frontend:**
  - `React Router`: Permite estructurar la aplicación como SPA sin recargas de página y gestionar rutas protegidas según el rol de usuario (coordinador, cuidador o familiar).
  - `Tailwind CSS`: Agiliza la maquetación de una interfaz accesible y reactiva para dispositivos móviles y escritorio sin redundancia de estilos.
  - `Vite`: Proporciona un entorno de desarrollo ultrarrápido con Hot Module Replacement (HMR) y empaquetado optimizado para despliegue.

- **Backend:**
  - `Express`: Framework minimalista y flexible sobre Node.js para estructurar la API REST mediante middlewares, modularizando rutas y autenticación.
  - `JSON Web Tokens (JWT)`: Implementa autenticación stateless segura para validar sesiones mediante tokens en cabeceras HTTP.
  - `bcrypt`: Cifrado y hashing seguro de contraseñas de usuarios en base de datos.
  - `CORS`: Configuración explícita de orígenes permitidos para la comunicación segura entre el cliente React y el servidor Express.

- **Base de datos (MongoDB Atlas + Mongoose):**
  - `Por qué`: Mongoose aporta tipado estricto y validaciones de esquemas en servidor sobre la base de datos documental MongoDB.
  - `Límites gratuitos`: Nivel **M0 Sandbox** en MongoDB Atlas, que incluye **512 MB de almacenamiento compartido**, suficiente para el volumen de datos de prueba del MVP.

- **Servicios externos (OpenRouteService API):**
  - `Por qué`: Geocodificación y cálculo de distancias y tiempos de desplazamiento óptimos entre los domicilios de los dependientes y la ubicación de los cuidadores.
  - `Límites gratuitos`: Plan estándar gratuito con **2.000 peticiones diarias** y un máximo de 40 peticiones por minuto para cálculo de rutas, margen que cubre con amplitud el desarrollo, los tests y la defensa del proyecto.

### Herramientas de desarrollo

| Para qué | Herramienta | Justificación |
| :--- | :--- | :--- |
| Editor de código | VS Code | Entorno compartido con configuración común mediante extensiones oficiales de ESLint y Prettier para homogeneizar el estilo de código. |
| Entorno de ejecución | Node.js v20 LTS | Misma versión fijada para todo el equipo para evitar discrepancias de compatibilidad y dependencias. |
| Pruebas de API | Postman / Thunder Client | Petición manual a los endpoints del servidor durante el desarrollo antes de conectarlos a las vistas. |
| Tests de Frontend | Vitest | Framework de tests unitarios rápido e integrado nativamente con Vite para verificar componentes de React. |
| Tests de Backend | Jest y Supertest | Pruebas de integración sobre las rutas, controladores y respuestas HTTP de Express. |
| Control de versiones | Git y GitHub | Gestión del código mediante ramas, seguimiento de issues y revisiones de Pull Requests. |

## 3. La gestión

### Tablero
La coordinación visual se gestiona mediante **GitHub Projects** asociado al repositorio:
- [Tablero de gestión de Cuidalia](https://github.com/ifonlob/Cuidalia/projects)
- **Flujo de trabajo por columnas:**
  - `Backlog`: Registro de ideas, requisitos funcionales pendientes y deuda técnica.
  - `Todo / Por hacer`: Tareas seleccionadas y estimadas para el sprint o hito activo.
  - `In Progress`: Tareas que un integrante del equipo está programando o documentando.
  - `In Review`: Tareas con Pull Request abierto que requieren revisión de código por otro compañero.
  - `Done`: Tareas aprobadas e integradas formalmente en la rama `develop`.
- **Trazabilidad:** Cada elemento del tablero nace de una Issue con asignación nominal y enlaza directamente con su rama de trabajo y Pull Request.

### Ramas
Se implementa una adaptación de GitFlow:
- `main`: Rama de producción. Solo almacena versiones estables, probadas y correspondientes a entregas finales.
- `develop`: Rama base de desarrollo e integración continua donde convergen las aportaciones del equipo.
- `Ramas de tarea`: Se ramifican siempre a partir de `develop` con prefijos según su cometido (`feat/`, `fix/`, `docs/`, `chore/`).
- **Reglas de protección:**
  - Tanto `main` como `develop` están protegidas desde la configuración del repositorio.
  - Quedan prohibidos los commits directos en ambas ramas.
  - Cualquier incorporación debe realizarse a través de un Pull Request dirigido a `develop`.
  - Todo PR requiere obligatoriamente al menos una revisión y aprobación (`Approve`) por parte de otro compañero antes de permitirse el merge.
  - Ningún miembro puede autoaprobar ni fusionar su propio PR.
  - Al completar un sprint o entrega oficial, se tramita un Pull Request desde `develop` hacia `main`.

### Estructura de carpetas
El proyecto se organiza bajo la estructura de monorepositorio requerida:

```text
Cuidalia/
├── client/                     # Código fuente de la aplicación frontend (React)
│   └── README.md               # Alcance del cliente y herramientas de interfaz
├── server/                     # Servidor backend y lógica de negocio (Node.js + Express)
│   └── README.md               # Documentación de endpoints, modelos y configuración
├── docs/                       # Documentación formal del proyecto
│   ├── CONTRATO.md             # Normas de convivencia, roles y canales del equipo
│   └── propuesta/              # Fases técnicas de la propuesta
│       ├── 00-brainstorming.md
│       ├── 01-problema.md
│       ├── 02-viabilidad-tecnica.md
│       ├── 03-objetivos-y-alcance.md
│       └── 04-recursos.md
├── .gitignore                  # Exclusiones de Git (node_modules, .env, temporales)
└── README.md                   # Portada del repositorio, problema, roles, stack y enlaces
