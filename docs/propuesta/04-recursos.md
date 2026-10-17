# Fase 4 · Recursos · <estudio>
## Introducción
## 1. Las personas
### Roles técnicos
  | Persona | Rol | De qué responde |
### Responsables por módulo
  | Módulo | Requisitos (RF) | Responsable | Apoyo |
### Comunicación     (enlace al contrato)
## 2. La tecnología

### Stack, servicios y APIs
La arquitectura tecnológica y la justificación de componentes se basan en lo definido en la fase anterior:
- Consulta en detalle: [Fase 2 · Viabilidad técnica](./02-viabilidad-tecnica.md)

**Resumen del stack y justificación:**
- **Frontend (React + Vite + Tailwind CSS):** Single Page Application que permite una navegación ágil y reactiva tanto en móvil como en escritorio. Tailwind agiliza el diseño modular y accesible para perfiles de familias y cuidadores.
- **Backend (Node.js + Express):** Entorno asíncrono y ligero para la construcción de una API REST modular, facilitando la gestión de peticiones concurrentes y la autenticación.
- **Base de datos (MongoDB + Mongoose):** Modelo documental NoSQL que aporta flexibilidad para modelar esquemas variables (perfiles de usuarios, historiales de asistencia, turnos y valoraciones). Se utiliza el nivel gratuito MongoDB Atlas (512 MB de almacenamiento), suficiente para el volumen de datos de prueba del MVP.
- **Servicios externos (OpenRouteService API):** Servicio para geocodificación, cálculo de distancias y optimización de rutas entre los domicilios de las familias y los cuidadores. Su plan gratuito ofrece 2.000 peticiones diarias, cubriendo con amplio margen las necesidades de demo y validación.

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
