# Fase 4 · Recursos · Cuidalia Studio
## Introducción
## 1. Las personas
### Roles técnicos
| Persona | Rol | De qué responde |
### Responsables por módulo
| Módulo | Requisitos (RF) | Responsable | Apoyo |
### Comunicación     (enlace al contrato)
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
