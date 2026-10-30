# Análisis de la competencia y del sector: CUIDALIA

## 1. Introducción y contexto del sector

El sector de la ayuda a domicilio (SAD) y la atención a personas dependientes en España crece de forma constante. Según datos del INE, más del 20% de la población supera ya los 65 años, lo que genera una demanda continua de cuidados respaldada por la Ley de Dependencia (Ley 39/2006).

Sin embargo, la mayoría de empresas que prestan este servicio (tanto pymes locales como concesionarias municipales) siguen trabajando con métodos poco digitalizados:

- **Cuadrantes manuales:** Los turnos y horarios se planifican en hojas de Excel sueltas o carpetas físicas, y los cambios de última hora se comunican por llamadas de teléfono o grupos de WhatsApp.
- **Gestión lenta de bajas imprevistas:** Cuando una cuidadora se pone enferma a primera hora de la mañana, la persona coordinadora tiene que llamar trabajadora por trabajadora para ver quién libra y puede cubrir la visita, lo que retrasa la atención y genera estrés en la oficina.
- **Falta de información para las familias:** Quienes contratan el servicio casi nunca saben en tiempo real si el auxiliar ha llegado a la hora, si la persona dependiente se ha tomado la medicación o si ha comido bien. Todo se reduce a una hoja de firmas a final de mes.
- **Dificultad para las auxiliares:** Las cuidadoras van de un domicilio a otro y necesitan consultar en el móvil las tareas, alergias y notas de cada persona sin tener que pasar por la oficina a recoger partes impresos.

**CUIDALIA** nace para resolver estos problemas mediante una aplicación web bajo modelo **B2B SaaS** (*Software as a Service*). Su objetivo es conectar en una sola plataforma a la coordinación de la empresa, al personal auxiliar y a los familiares, facilitando sobre todo la gestión de bajas y el seguimiento de las visitas en tiempo real.

Para conocer el mercado antes de construir el producto y cumplir con el Criterio 1a, en este documento analizamos 6 empresas competidoras directas e indirectas que operan en España.

---

## 2. Metodología de análisis

Hemos seleccionado 6 empresas representativas del sector y las hemos evaluado bajo los criterios exigidos en la guía:

1. **Tamaño:** Startup, PYME o gran empresa / scaleup.
2. **Modelo de negocio:** B2B (a empresas), B2C (a particulares), B2B2C o C2C / marketplace, con sus métodos de cobro (suscripción mensual, comisión o tarifa fija).
3. **Alcance geográfico:** Local, provincial, autonómico o nacional.
4. **Organización interna:** Tipo de estructura (jerárquica, funcional, matricial u horizontal), número aproximado de empleados y tecnologías que usan (a partir de ofertas de empleo, datos públicos y análisis web).
5. **Producto y servicio:** Funcionalidades clave, propuesta de valor, precios estimados, puntos fuertes y puntos débiles.

---

## 3. Análisis individual de competidores

### 3.1. GESAD (Grupo Trevenque)

- **Qué hace:** Es el software de gestión de ayuda a domicilio más implantado en España, desarrollado en Granada por Grupo Trevenque. Lleva más de 25 años en el mercado y lo utilizan grandes empresas concesionarias y ayuntamientos para gestionar contratos públicos de dependencia.
- **Tamaño:** Gran empresa (Grupo Trevenque cuenta con más de 200 empleados en total; unos 40 trabajan directamente en el área de Gesad).
- **Modelo de negocio:** B2B tradicional y SaaS institucional. Cobran por licencias de usuario, implantación y mantenimiento mensual a grandes empresas del sector.
- **Alcance:** Nacional (gestiona más de 120.000 usuarios de ayuda a domicilio en toda España).
- **Estructura organizativa:** Jerárquica tradicional con departamentos separados: Dirección, Consultoría, Desarrollo, Soporte y Sistemas.
- **Tecnologías que utiliza:**
  - Sistema cliente-servidor clásico en .NET, lenguaje C# y bases de datos Microsoft SQL Server.
  - Tienen una aplicación móvil complementaria (*Gesad Mobile*) para Android e iOS orientada al fichaje en domicilio con códigos QR o etiquetas NFC.
  - Infraestructura alojada en su propio centro de datos (*Cloud Center Andalucía*).
- **Funcionalidades principales:** Gestión de cuadrantes masivos anuales, facturación adaptada a los pliegos de contratación pública, cálculo de nóminas bajo convenio sociosanitario e informes oficiales para administraciones.
- **Propuesta de valor:** Cumplimiento normativo y control administrativo estricto para grandes licitaciones públicas de SAD.
- **Precios y condiciones:** Presupuesto a medida con costes de implantación altos (entre 3.000 € y más de 15.000 € según el tamaño de la entidad), más licencias por puesto y cuotas mensuales de soporte.
- **Puntos fuertes:** Gran conocimiento de los pliegos públicos, cálculo de nóminas muy fiable y alta implantación en grandes contratas.
- **Puntos débiles:** Interfaz antigua, difícil de usar y con una curva de aprendizaje larga; cuadrantes muy rígidos para cambios rápidos de última hora; no ofrece una aplicación clara para las familias; y tiene precios fuera del alcance de pequeñas cooperativas o pymes locales.

---

### 3.2. CUIDEO (Cuideo Care S.L.)

- **Qué hace:** Plataforma digital fundada en Barcelona en 2016 que funciona como agencia de colocación de cuidadores para familias particulares.
- **Tamaño:** Scaleup / Mediana empresa (entre 120 y 200 personas en oficina central).
- **Modelo de negocio:** B2C (cobran una cuota inicial de selección a la familia y una mensualidad por gestionar nóminas y sustituciones), con acuerdos B2B2C con aseguradoras.
- **Alcance:** Nacional, con oficinas comerciales en Barcelona, Madrid, Sevilla, Bilbao y Valencia.
- **Estructura organizativa:** Funcional orientada a crecimiento rápido (*growth*): Selección de personal, Producto/Tecnología, Ventas y Operaciones.
- **Tecnologías que utiliza:**
  - Web pública y panel en React y Next.js.
  - Backend en Node.js y PHP con CRM (Salesforce / HubSpot) y pagos con Stripe.
  - Servidores en la nube (AWS).
- **Funcionalidades principales:** Búsqueda rápida de cuidadores con referencias en 24-48 horas, redacción de contratos de empleados de hogar, altas en la Seguridad Social y gestión mensual de nóminas.
- **Propuesta de valor:** Contratar a un cuidador verificado con respaldo legal en menos de 48 horas sin papeleos para la familia.
- **Precios y condiciones:** Tarifa inicial de selección de 250 € a 450 €, más una cuota mensual de mantenimiento laboral de entre 50 € y 90 € al mes.
- **Puntos fuertes:** Marca muy conocida, captación rápida de cuidadores y trámite legal completo para la familia.
- **Puntos débiles:** No venden software a empresas de ayuda a domicilio (compiten contra ellas como agencia privada); su modelo es de un cuidador fijo por domicilio, sin herramientas para coordinar rutas por horas; y las cuotas resultan caras para muchas familias.

---

### 3.3. QIDA (Qida Cuidado Integral S.L.)

- **Qué hace:** Empresa de cuidados domiciliarios fundada en 2018 con certificación de impacto social (B-Corp). Combina el cuidado de personas dependientes con la supervisión clínica de terapeutas y enfermeros, colaborando con hospitales y mutuas.
- **Tamaño:** Scaleup (entre 150 y 250 empleados en estructura).
- **Modelo de negocio:** B2C y B2B2C mediante convenios con centros hospitalarios para gestionar altas de pacientes dependientes.
- **Alcance:** Nacional (con foco en Cataluña, Madrid y Zaragoza).
- **Estructura organizativa:** Matricial, combinando un equipo sanitario (coordinadores de caso que son trabajadores sociales o enfermeros) con equipos de producto digital y operaciones.
- **Tecnologías que utiliza:**
  - Microservicios en Google Cloud Platform y AWS.
  - Aplicaciones móviles en React Native y Flutter para familias y personal cuidador.
- **Funcionalidades principales:** Planes de cuidados individualizados supervisados por personal sanitario, seguimiento de salud desde la app móvil, gestión laboral de contratos y atención telefónica continua.
- **Propuesta de valor:** Cuidado domiciliario de base sociosanitaria para que personas con patologías crónicas puedan seguir viviendo en su casa con seguimiento médico.
- **Precios y condiciones:** Valoración inicial de unos 200 € - 300 €, sumada a los costes de salario regulado y cuotas de gestión mensual.
- **Puntos fuertes:** Gran nivel asistencial, seguimiento de la salud real del usuario y buena integración con el sistema médico.
- **Puntos débiles:** Servicio costoso para el usuario medio y plataforma tecnológica totalmente cerrada para uso interno, sin opción de licenciamiento para empresas externas de SAD.

---

### 3.4. CUIDUM (Tu Selección Digital S.L.)

- **Qué hace:** Plataforma valenciana creada en 2015 especializada en la selección telemática de cuidadores para personas mayores, con especial foco en régimen interno (24 horas).
- **Tamaño:** PYME (unos 40 a 70 empleados).
- **Modelo de negocio:** B2C de intermediación y asesoría laboral para familias.
- **Alcance:** Nacional (gestión telemática en toda España).
- **Estructura organizativa:** Funcional: Selección con psicólogos, Departamento Laboral, Asesoría Legal y Atención al Cliente.
- **Tecnologías que utiliza:**
  - Portal web en PHP y JavaScript con bases de datos relacionales.
  - Batería de test psicométricos online propios para evaluar a las candidatas.
- **Funcionalidades principales:** Filtro psicológico de cuidadores, tramitación de contratos y nóminas en el Régimen de Empleados de Hogar y sustitución del cuidador si la familia no está satisfecha o hay una baja.
- **Propuesta de valor:** Selección psicológica rigurosa para asegurar cuidadores de confianza en estancias largas o cuidados internos.
- **Precios y condiciones:** Alta inicial de 250 € a 400 € y cuota mensual de gestión en torno a 60 €/mes.
- **Puntos fuertes:** Buen sistema de filtrado previo de candidatas y experiencia contrastada en cuidadores internos.
- **Puntos débiles:** La plataforma solo gestiona el alta y las nóminas, pero no permite hacer seguimiento diario de tareas ni check-in en el domicilio; no sirve para empresas con plantilla propia de auxiliares.

---

### 3.5. FAMILIADOS (Familiados Care S.L.)

- **Qué hace:** Startup nacida en Navarra que funciona como una aplicación para buscar cuidadores verificados por horas, para situaciones puntuales o de emergencia (ingresos hospitalarios, fines de semana o relevos familiares).
- **Tamaño:** Startup pequeña (entre 12 y 25 personas).
- **Modelo de negocio:** Marketplace C2C y B2C. Cobran comisión por cada hora reservada a través de la app y una suscripción opcional (*Familiados Pro*).
- **Alcance:** Nacional.
- **Estructura organizativa:** Horizontal y ágil, con un equipo pequeño centrado en producto móvil, atención y marketing.
- **Tecnologías que utiliza:**
  - Aplicaciones móviles en iOS y Android.
  - Backend en la nube (Google Cloud Platform) con bases de datos NoSQL y chat en tiempo real.
- **Funcionalidades principales:** Búsqueda geolocalizada de cuidadores disponibles en menos de 1 hora, perfiles con opiniones de otros usuarios, mensajería integrada y pago automático por la app.
- **Propuesta de valor:** Encontrar a una persona de confianza para un cuidado urgente en cuestión de minutos y desde el móvil.
- **Precios y condiciones:** Precio por hora fijado en la app (habitualmente entre 10 € y 18 €/hora) con comisión por servicio.
- **Puntos fuertes:** Rapidez de respuesta en urgencias y una aplicación móvil muy sencilla e intuitiva.
- **Puntos débiles:** Mucha rotación de personal, no pensada para tratamientos de dependencia continuados y sin encaje para empresas de SAD con cuadrantes fijos.

---

### 3.6. AIUDO (Aiudo Care S.L.)

- **Qué hace:** Empresa de cuidados domiciliarios creada en Valencia que se diferencia por usar cuestionarios de personalidad y compatibilidad para asignar el cuidador que mejor encaje con el carácter del anciano.
- **Tamaño:** PYME (entre 25 y 45 personas).
- **Modelo de negocio:** B2C de intermediación y gestión de nóminas para particulares.
- **Alcance:** Nacional.
- **Estructura organizativa:** Funcional: psicólogos de selección, gestores de familias y administración.
- **Tecnologías que utiliza:**
  - Web interactiva con cuestionarios de afinidad y CRM de seguimiento.
- **Funcionalidades principales:** Test de compatibilidad dependiente-cuidador, contratación en el régimen de hogar, gestión de nóminas y seguimiento telefónico con la familia.
- **Propuesta de valor:** Reducir el rechazo inicial al cuidador buscando perfiles compatibles en aficiones, carácter y forma de ser.
- **Precios y condiciones:** Cuota inicial de búsqueda de unos 300 € y cuota mensual de gestión de nóminas de 55 € a 75 €/mes.
- **Puntos fuertes:** Buen trato humano y foco en evitar conflictos de convivencia en el domicilio.
- **Puntos débiles:** Modelo de agencia tradicional con baja automatización técnica; no resuelve la gestión de cuadrantes ni el seguimiento diario de servicios por horas.

---

## 4. Tabla comparativa de competidores

| Empresa | Tipo y tamaño | Modelo de negocio | Alcance | Empleados aprox. | Tecnologías principales | Propuesta de valor | Precios estimados | Puntos fuertes | Puntos débiles |
|---|---|---|---|:---:|---|---|---|---|---|
| **GESAD** | Gran empresa | B2B institucional / Licencias | Nacional | > 200 (grupo) | .NET, C#, SQL Server, Gesad Mobile | Gestión integral para pliegos públicos de SAD | Alta inversión (> 3.000 € alta + cuotas) | Muy adaptado a pliegos y nóminas complejas | Interfaz antigua, difícil de usar y cara para pymes |
| **CUIDEO** | Scaleup | B2C agencia digital | Nacional | 120 - 200 | React, Next.js, Node.js, AWS, Salesforce | Cuidador verificado con contrato legal en 48 h | Alta de 300 € + 60-90 €/mes | Marca reconocida y trámite legal rápido | No vende software a empresas; solo atiende a particulares |
| **QIDA** | Scaleup B-Corp | B2C y B2B2C sociosanitario | Nacional | 150 - 250 | GCP, AWS, React Native / Flutter | Atención en el hogar con seguimiento médico y enfermería | Coste alto según horas y seguimiento | Gran rigor asistencial y app familiar útil | Precio alto y tecnología cerrada de uso interno |
| **CUIDUM** | PYME | B2C agencia de colocación | Nacional | 40 - 70 | Web PHP/JS, test psicométricos propios | Cuidadores internos seleccionados por psicólogos | Alta de 300 € + 60 €/mes | Buen filtro de perfiles para régimen interno | Sin seguimiento de visitas en directo ni gestión de turnos |
| **FAMILIADOS** | Startup | C2C / B2C on-demand | Nacional | 12 - 25 | Apps iOS/Android, GCP, bases NoSQL | Cuidadores por horas en menos de 1 hora | Comisión por hora (10 - 18 €/h) | Inmediatez y app muy fácil de usar | Alta rotación de cuidadores; no sirve para cuidados crónicos |
| **AIUDO** | PYME | B2C intermediación | Nacional | 25 - 45 | Web interactiva, CRM y test de compatibilidad | Emparejamiento por afinidad personal y carácter | Alta de 300 € + 55-75 €/mes | Enfoque empático y personal | Procesos manuales sin cuadrantes ni control de visitas |
| **CUIDALIA** | **Startup (MVP)** | **B2B SaaS (suscripción pymes)** | **Autonómico / Local inicial** | **4 (equipo dev)** | **Stack MERN, Vite, Tailwind CSS, PWA, OpenRouteService** | **Coordinación de sustituciones con rutas y app para familias** | **Cuota mensual asequible para empresas de SAD** | **Sustituciones automáticas por cercanía, PWA ligera y visibilidad familiar** | **Producto en fase inicial de validación** |

---

## 5. Oportunidades detectadas y ventajas de CUIDALIA

Tras comparar el mercado, identificamos cuatro oportunidades claras para el proyecto:

### 1. El hueco entre los ERPs pesados y las agencias privadas
Las empresas pequeñas y medianas de SAD no pueden pagar los miles de euros que cuesta implantar GESAD ni necesitan módulos administrativos tan complejos. Al mismo tiempo, plataformas como Cuideo o Cuidum no les ofrecen software, sino que les quitan clientes porque van directo a la familia. CUIDALIA ocupa ese espacio intermedio: una herramienta web ágil y asequible pensada para que la propia empresa gestione mejor a sus auxiliares y sus servicios.

### 2. Sustituciones inmediatas con cálculo de rutas reales
En las empresas tradicionales, cuando alguien avisa de una baja a las 7 de la mañana, la coordinadora pierde horas llamando por teléfono. CUIDALIA automatiza este proceso:
- Filtra qué trabajadoras cumplen los requisitos del usuario (uso de grúa, experiencia con demencias o alergias a mascotas).
- Con la API de **OpenRouteService**, calcula la distancia y el tiempo real de traslado entre los domicilios según el medio de transporte (coche, bici o a pie), ordenando a las candidatas por cercanía.
- Lanza una notificación web a las trabajadoras disponibles y la primera que pulsa "Aceptar" en su móvil se queda con el servicio, actualizando el cuadrante al instante sin llamadas.

### 3. Información en tiempo real para las familias
Casi ningún competidor B2B deja que la familia consulte qué pasa en el domicilio. En CUIDALIA, el familiar puede abrir la app y ver:
- El fichaje de entrada y salida con geolocalización (*check-in* y *check-out*).
- Las tareas marcadas (aseo, comida, paseo).
- El registro de la medicación administrada y notas sobre el estado de ánimo.
- Avisos inmediatos si ocurre una caída o un imprevisto.

### 4. Una aplicación web progresiva (PWA) sin instalaciones pesadas
En lugar de obligar a instalar programas pesados en el ordenador o apps grandes desde Google Play o App Store, CUIDALIA utiliza el **stack MERN y arquitectura PWA**:
- Funciona en cualquier navegador de ordenador, tablet o móvil.
- Se puede instalar como icono directo en la pantalla del teléfono ocupando muy poco espacio.
- Permite enviar notificaciones push web mediante el estándar VAPID sin coste adicional de mensajería.
- Se adapta bien a teléfonos móviles modestos, que son los que habitualmente utiliza el personal auxiliar en sus desplazamientos diarios.

---

## 6. Conclusiones para el MVP

Para que el proyecto sea viable dentro del plazo previsto y con los recursos del equipo, aplicaremos las siguientes decisiones:

1. **Priorizar el recorrido clave:** No intentaremos hacer un programa de nóminas ni de contabilidad como GESAD. El MVP debe centrarse en lo que aporta valor inmediato: **cuadrantes, resolución rápida de bajas por cercanía y la vista diaria para la familia**.
2. **Validar con datos sintéticos y empresas locales:** Haremos pruebas con casos ficticios basados en empresas y cooperativas de ayuda a domicilio de nuestro entorno (provincia de Cádiz y Andalucía).
3. **Cuidar la sencillez de uso:** La interfaz debe ser clara y limpia para que una coordinadora o una auxiliar aprenda a usarla en 10 minutos sin necesidad de manuales complejos.
4. **Respetar la seguridad y privacidad:** Dado que manejamos datos sensibles (salud y domicilios), mantendremos autenticación segura por roles (JWT con cookies `httpOnly`), respetando lo recogido en `docs/legislacion.md`.
