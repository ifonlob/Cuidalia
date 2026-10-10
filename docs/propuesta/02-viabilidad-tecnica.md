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

| Tecnología | Irene | Dani | Alejandro | Pablo |
|---|:---:|:---:|:---:|:---:|
| HTML y CSS | 4 | 3 | 3 | 3 |
| JavaScript (ES6+, async/await) | 3 | 3 | 2 | 2 |
| React (componentes, hooks, props) | 0 | 2 | 0 | 0 |
| React Router | 0 | 2 | 0 | 0 |
| Tailwind CSS | 3 | 2 | 2 | 2 |
| Vite | 0 | 3 | 0 | 0 |
| TanStack Query | 0 | 0 | 0 | 0 |
| Axios | 0 | 0 | 0 | 0 |
| React Hook Form + Zod | 0 | 0 | 0 | 0 |
| PWA (vite-plugin-pwa) y notificaciones push | 0 | 0 | 0 | 0 |
| Node.js | 1 | 0 | 0 | 0 |
| Express (rutas, middlewares) | 0 | 0 | 0 | 0 |
| Autenticación con JWT (access y refresh token) | 0 | 0 | 0 | 0 |
| bcrypt y seguridad básica (helmet, CORS) | 0 | 0 | 0 | 0 |
| Control de acceso por roles | 2 | 1 | 0 | 0 |
| MongoDB y Mongoose | 1 | 1 | 1 | 1 |
| Diseño de esquemas e índices | 4 | 2 | 2 | 3 |
| Consumo de APIs externas (OpenRouteService) | 3 | 3 | 3 | 3 |
| Git y GitHub (ramas, PR, review) | 5 | 3 | 3 | 3 |
| Despliegue (Vercel, Render, Atlas) | 1 | 2 | 1 | 1 |
| Testing (opcional) | 3 | 4 | 0 | 0 |

---

### 3.2 Lagunas de conocimiento

| Tecnología o tema | Quién la desconoce | Qué hay que aprender | Cómo y cuándo se aprende | Tiempo estimado |
|---|---|---|---|:---:|
| PWA y notificaciones push | Irene, Pablo, Alejandro | Service Workers y suscripción push | Documentación oficial y spike técnico en sprint 2 | 8 h |
| React Hook Form + Zod | Irene, Pablo, Alejandro, Dani | Validación de esquemas en formularios | Mini-módulo de autenticación en semana 1 | 5 h |
| Control de roles con JWT | Irene, Pablo, Alejandro, Dani | Middleware de autorización en Express | Integración de endpoints protegidos en sprint 1 | 6 h |
| OpenRouteService | Irene, Pablo, Alejandro, Dani | Consumo de API REST y cálculo de rutas | Pruebas de integración previas al cuadrante | 4 h |

---

#### Valoración
- ¿Las horas estimadas caben en las horas disponibles?: Sí. El alcance planteado para el MVP es totalmente asumible dentro del tiempo previsto. La carga de trabajo se distribuye de manera equilibrada y no supera la disponibilidad global, permitiendo absorber los tiempos de aprendizaje.

#### Recortes del MVP
- No es necesario aplicar ningún recorte. La planificación temporal y la capacidad del equipo permiten abordar la totalidad de las funcionalidades definidas para el MVP.
- Se desarrolla el 100% del alcance comprometido:
  - Gestión integral de cuadrantes y perfiles de usuarios asistidos (CU-C1, CU-C3).
  - Circuito de sustituciones y sistema de notificaciones (CU-C4, CU-C5, CU-T2).
  - Interfaz de trabajo del cuidador con agenda, check-in/out y checklist (CU-T1, CU-T3, CU-T5, CU-T6).
  - Panel de monitorización en tiempo real para coordinación (CU-C6).
  - Módulo de resumen diario y seguimiento para familiares (CU-F1).
    
---

## 4. Riesgos técnicos
### 4.1 Listado de riesgos

### 4.2 Estrategias de mitigación
