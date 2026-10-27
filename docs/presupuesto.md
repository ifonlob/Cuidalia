# Presupuesto Económico y Control de Costes - CUIDALIA

Este documento recoge la planificación financiera, las tarifas horarias, las estimaciones de esfuerzo y el control de costes reales del proyecto CUIDALIA durante sus 6 sprints de desarrollo.


## 1. Definición Razonada de Perfiles y Tarifas por Hora

El coste del proyecto se fundamenta en el esfuerzo humano requerido para el desarrollo del stack MERN. Tomando como referencia las tablas salariales del sector tecnológico en España y calculando el coste total de empresa, se fijan tres perfiles operativos:

| Perfil | Rango de Mercado | Tarifa Asignada | Justificación y Aplicación en CUIDALIA |
| :--- | :---: | :---: | :--- |
| **Junior Developer** | 15 - 25 €/h | **20,00 €/h** | Perfil base de desarrollo asumido por el equipo. Abarca maquetación de vistas en React, maquetación responsive con Tailwind CSS, validación de formularios con React Hook Form/Zod, rutas API básicas y pruebas unitarias de componentes. |
| **Mid Developer** | 30 - 45 €/h | **35,00 €/h** | Se aplica a tareas de mayor complejidad técnica: modelado de esquemas complejos en Mongoose, optimización de consultas de cuadrantes, lógica de validación de conflictos horarios, integración de la API de OpenRouteService y control de estados globales. |
| **Senior / Tech Lead** | 50 - 80 €/h | **60,00 €/h** | Reservado para la toma de decisiones arquitecturales críticas: diseño de seguridad y autorización JWT, configuración de pipelines de CI/CD, aprovisionamiento de infraestructura en la nube (Render, Vercel, MongoDB Atlas) y auditoría de protección de datos (RGPD). |

---

## 2. Planificación Presupuestaria Global

El proyecto se estructura en 6 sprints de 2 semanas de duración cada uno, con una asignación media estimada de 10 horas semanales por integrante (40 horas de equipo por semana / 80 horas de equipo por sprint):

| Sprint | Objetivo Principal | Perfiles Ponderados | Horas Estimadas | Coste Estimado (€) |
| :--- | :--- | :--- | :---: | :---: |
| **Sprint 1** | Configuración inicial, arquitectura MERN y modelos base | Junior (70%), Mid (20%), Senior (10%) | 80 h | 2.160,00 € |
| **Sprint 2** | Autenticación, roles y control de acceso (JWT, Hash) | Junior (50%), Mid (30%), Senior (20%) | 80 h | 2.600,00 € |
| **Sprint 3** | Cuadrantes, listado de turnos y filtrado de bajas | Junior (60%), Mid (40%) | 80 h | 2.080,00 € |
| **Sprint 4** | Recorrido MVP: disponibilidad, asignación y aceptación | Junior (60%), Mid (40%) | 80 h | 2.080,00 € |
| **Sprint 5** | Pruebas de integración, seguridad, accesibilidad y RGPD | Junior (60%), Mid (25%), Senior (15%) | 80 h | 2.360,00 € |
| **Sprint 6** | Despliegue en producción (Vercel/Render), CI/CD y cierre | Junior (50%), Senior (50%) | 80 h | 3.200,00 € |
| **Totales** | | | **480 h** | **14.480,00 €** |

---

## 4. Registro y Comparativa: Estimación vs. Realidad

### Sprint 1: Configuración del Entorno y Arquitectura Base

> Este desglose refleja las tareas planificadas para el inicio del proyecto. Las columnas de horas reales, desviación y coste real se completarán al cierre del sprint con los datos registrados en Toggl Track.

| Issue | Tarea / Entregable | Responsable | Perfil | Horas Estimadas | Desviación (h) | Coste Estimado (€) | Coste Real (€) | Desviación (€) |
| :---: | :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| #1 | Inicialización del repositorio y estándares Git | Dani | Junior | 8 h | - | 160,00 € | - | - |
| #2 | Configuración del servidor Express.js y scripts | Irene | Junior | 12 h | - | 240,00 € | - | - |
| #3 | Inicialización del cliente frontend (React + Vite) | Dani | Junior | 12 h | - | 240,00 € | - | - |
| #4 | Conexión y configuración de cluster MongoDB Atlas | Alejandro | Mid | 10 h | - | 350,00 € | - | - |
| #5 | Definición inicial de esquemas de datos (Mongoose) | Pablo | Mid | 14 h | - | 490,00 € | - | - |
| #6 | Definición de arquitectura modular y estructura base | Alejandro | Senior | 8 h | - | 480,00 € | - | - |
| #7 | Documentación inicial de arquitectura y endpoints | Pablo | Junior | 8 h | - | 160,00 € | - | - |
| #8 | Formación técnica inicial del stack (React / Express) | Equipo | Junior | 8 h | - | 160,00 € | - | - |
| **Total** | **Sprint 1** | | | **80 h** | **-** | **2.280,00 €** | **-** | **-** |

*(Nota: Las tablas de los Sprints 2 al 6 se generarán al inicio de cada iteración durante su correspondiente Sprint Planning).*

---

## 5. Análisis de Desviaciones y Mejora Continua

Durante la reunión de *Sprint Retrospective* al término de cada sprint, el equipo auditará los desvíos entre las horas presupuestadas y las registradas en Toggl Track para calibrar la velocidad del siguiente ciclo:

### Plantilla de Auditoría (Sprint 1)
- **Tareas con sobrecoste temporal (desviación positiva):**
  - *Identificador y tarea:* [Indicar issue]
  - *Causa identificada:* [Ejemplo: Dificultad en la configuración de CORS / variables de entorno en Vite / problemas de conexión con Atlas].
  - *Impacto económico:* [Diferencia en euros respecto al presupuesto].
- **Tareas con rendimiento optimizado (desviación negativa):**
  - *Identificador y tarea:* [Indicar issue]
  - *Causa identificada:* [Ejemplo: Reutilización de boilerplate previo / resolución ágil].
- **Medidas correctoras para el Sprint 2:**
  - Descomponer tareas que superen las 8 horas estimadas en subtareas más específicas.
  - Dedicar los primeros 30 minutos de las tareas de mayor incertidumbre a consultar la documentación técnica de forma conjunta.

---

## 6. Costes Adicionales: Infraestructura, Servicios y Licencias

Para el despliegue del MVP y la operación de CUIDALIA se contempla una estrategia basada en niveles gratuitos (free-tier) para desarrollo, proyectando el coste comercial en caso de escalado:

| Concepto / Servicio | Proveedor | Plan / Especificaciones | Coste Mensual (€) | Coste Fase Desarrollo (3 meses) | Coste Estimado Producción Comercial (€/mes) |
| :--- | :--- | :--- | :---: | :---: | :---: |
| **Alojamiento Frontend** | Vercel | Hobby Tier (SSL, CDN global) | 0,00 € | 0,00 € | 20,00 € |
| **Alojamiento Backend** | Render | Free Web Service (Node.js runtime) | 0,00 € | 0,00 € | 7,00 € (Plan Starter) |
| **Base de Datos Cloud** | MongoDB Atlas | Cluster M0 Sandbox (512 MB Storage) | 0,00 € | 0,00 € | 9,00 € (Cluster M2) |
| **Cálculo de Rutas / Mapas** | OpenRouteService | Standard Free (2.000 req/día) | 0,00 € | 0,00 € | 0,00 € |
| **Gestión y Tableros** | GitHub Projects | Plan Free (Integrado en repo) | 0,00 € | 0,00 € | 0,00 € |
| **Control de Tiempo** | Toggl Track | Free Plan (Hasta 5 usuarios) | 0,00 € | 0,00 € | 0,00 € |
| **Dominio Personalizado** | Namecheap / DonDominio | Dominio corporativo `.es` o `.org` | - | 12,00 € (Anual) | 1,00 € / mes amortizado |
| **Total Servicios** | | | **0,00 €** | **12,00 €** | **37,00 € / mes** |

---

## 7. Presupuesto Total del Proyecto

Resumen del coste global presupuestado para la entrega del MVP de CUIDALIA:

| Partida Presupuestaria | Base Estimada (€) | Real Ejecutado (€) | Desviación Acumulada (€) |
| :--- | :---: | :---: | :---: |
| Mano de Obra: Sprint 1 | 2.280,00 € | - | - |
| Mano de Obra: Sprint 2 | 2.600,00 € | - | - |
| Mano de Obra: Sprint 3 | 2.080,00 € | - | - |
| Mano de Obra: Sprint 4 | 2.080,00 € | - | - |
| Mano de Obra: Sprint 5 | 2.360,00 € | - | - |
| Mano de Obra: Sprint 6 | 3.200,00 € | - | - |
| **Subtotal Mano de Obra (480 horas)** | **14.600,00 €** | **-** | **-** |
| Infraestructura, Licencias y Dominios | 12,00 € | - | - |
| Margen de Contingencia Técnica (10%) | 1.461,20 € | - | - |
| **PRESUPUESTO TOTAL ESTIMADO** | **16.073,20 €** | **-** | **-** |
