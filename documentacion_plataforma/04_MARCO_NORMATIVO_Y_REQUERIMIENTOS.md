# 01 - Especificación de Requerimientos del Sistema
## Suite de Juegos Serios 3D - Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Gerencia de Prevención y SST

---

## 1. Alcance y Contexto del Proyecto

La suite formativa está compuesta por **cinco (5) simulaciones interactivas en 3D** diseñadas como Objetos Virtuales de Aprendizaje (OVA) para fortalecer las habilidades de autorregulación emocional, gestión de la carga mental, prevención de la fatiga, bienestar financiero y comunicación asertiva en trabajadores expuestos a factores de riesgo psicosocial de alto impacto (sector construcción y operaciones afines).

Las soluciones cumplen con las directrices de la **Resolución 2764 de 2022** (Batería de Instrumentos de Evaluación de Factores de Riesgo Psicosocial del Ministerio del Trabajo de Colombia), la **Ley 1010 de 2006** (Prevención y corrección del acoso laboral) y la **Ley 2460 de 2025** (Desconexión laboral efectiva).

---

## 2. Requerimientos Funcionales (RF)

| ID | Requerimiento Funcional | Descripción y Criterio de Aceptación | Módulos Impactados |
| :--- | :--- | :--- | :--- |
| **RF-01** | **Renderizado 3D en Tiempo Real** | Cada simulación debe cargar una escena tridimensional interactiva utilizando WebGL / Three.js sin requerir plugins externos ni dependencias pesadas compiladas. | Todos (Juegos 1 al 5) |
| **RF-02** | **Interacción y Toma de Decisiones** | El usuario debe enfrentarse a situaciones reales de obra donde sus decisiones determinen un impacto directo en el clima laboral, la fatiga somática o la carga mental de la cuadrilla. | Todos (Juegos 1 al 5) |
| **RF-03** | **Secuencia de Resolución Somática 3D** | En situaciones de alta intensidad emocional, el juego debe ejecutar una secuencia vivencial guiada: 1) Actúa y respira con guía somática, 2) Expresión asertiva con voz, 3) Intervención de apoyo en terreno (SST), y 4) Cierre reflexivo. | Juego 5 |
| **RF-04** | **Síntesis de Voz y Subtitulado** | Diálogos principales con síntesis de voz natural en español mediante Web Speech API, acompañada de subtítulos sincronizados de alto contraste para accesibilidad total (WCAG 2.1 AA). | Juego 5, Juego 1 |
| **RF-05** | **Evaluación y Diagnóstico** | Puntuación cuantificable sobre escala de 0 a 100 puntos. Umbral de aprobación fijado en **80 puntos**. Generación de informe final detallado con fortalezas y oportunidades de mejora. | Todos (Juegos 1 al 5) |
| **RF-06** | **Persistencia SCORM y Fallback** | Integración transparente con API SCORM (`cmi.core.lesson_status`, `cmi.core.score.raw`, `cmi.suspend_data`). Si se ejecuta fuera de un LMS, el sistema debe operar en modo autónomo sin arrojar errores. | Todos (Juegos 1 al 5) |

---

## 3. Requerimientos No Funcionales (RNF)

### 3.1 Rendimiento y Eficiencia
* **RNF-01 (Tiempo de Carga):** La carga inicial de cada juego no debe superar los 3 segundos en conexiones de banda ancha estándar (10 Mbps), y debe operar fluidamente en redes móviles de obra.
* **RNF-02 (Tasa de Fotogramas):** Mínimo 45-60 FPS sostenidos en equipos con gráficos integrados (Intel UHD Graphics 620 o superior).
* **RNF-03 (Peso de Paquete):** Los paquetes comprimidos `.zip` SCORM deben pesar menos de 500 KB para garantizar descargas instantáneas en servidores LMS corporativos.

### 3.2 Usabilidad y Diseño
* **RNF-04 (Diseño Responsivo):** Interfaz fluida adaptable a resoluciones móviles verticales/horizontales (smartphones, tablets) y monitores de escritorio (1280x720, 1920x1080).
* **RNF-05 (Identidad Visual Seguros Bolívar):** Paleta corporativa sobria (Azul `#023047`, Amarillo `#FFB703`, Verde `#2A9D8F`), tipografía *Plus Jakarta Sans* y componentes translúcidos con *glassmorphism*.
* **RNF-06 (Iconografía Vectorial Estricta):** 100% vector SVG nativo; cero uso de emojis de mensajería informal, garantizando una imagen formal e institucional.

### 3.3 Compatibilidad y Soporte de Plataforma
* **RNF-07 (Navegadores):** Google Chrome (v90+), Microsoft Edge (v90+), Mozilla Firefox (v88+), Safari (v14+).
* **RNF-08 (Estándares E-Learning):** Total conformidad con los estándares SCORM 1.2 (ADL) y SCORM 2004 (3ª y 4ª Edición).

---

## 4. Requerimientos de Seguridad y Privacidad
* **Seguridad de Datos:** Las simulaciones no capturan ni almacenan datos biométricos, personales ni cédulas de ciudadanía en servidores externos. Toda la trazabilidad se limita a los identificadores anónimos de sesión gestionados directamente por el LMS de la organización.
* **Integridad de Contenido:** Ejecución estricta bajo HTTPS o protocolo local seguro, sin inyección de scripts externos no autenticados.

