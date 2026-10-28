# 02 - Arquitectura Técnica y Estructura de Software
## Suite de Juegos Serios 3D - Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Gerencia de Prevención y SST

---

## 1. Visión General de la Arquitectura

Las simulaciones siguen un patrón arquitectónico desacoplado basado en **Micro-aplicaciones Front-End Autónomas (Single-File SPA)** empaquetadas como Objetos Virtuales de Aprendizaje (OVA). Cada juego integra de forma nativa su motor de renderizado 3D, lógica de estado, interfaz gráfica y capa de telemetría e-learning sin requerir un backend intermediario.

```
+-----------------------------------------------------------------------------------+
|                            CAPA DE PRESENTACIÓN (UI / UX)                         |
|  - Canvas WebGL (Three.js r128)          - Capas HTML5 Glassmorphism              |
|  - Iconografía Vectorial SVG Estricta   - Tipografía Plus Jakarta Sans            |
|  - Banners de Subtítulos Sincronizados   - Guías Somáticas y Chips de Paso        |
+-----------------------------------------------------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                         CAPA DE CONTROL Y LÓGICA DE JUEGO                         |
|  - Máquina de Estados Finita (FSM: Intro -> Escenario -> Elección -> Feedback)     |
|  - Motor de Audio Somático y Web Speech API (Voz en Español)                      |
|  - Sistema de Puntuación Dinámica y Diagnóstico Psicosocial (0 - 100 pts)         |
+-----------------------------------------------------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                        CAPA DE COMUNICACIÓN E INTEGRACIÓN LMS                     |
|  - Envoltorio Universal SCORM 1.2 / 2004                                          |
|  - Sincronización de Sesión (cmi.core.lesson_status, score.raw, session_time)     |
|  - Serialización de Reanudación (cmi.suspend_data en JSON)                        |
|  - Controlador de Fallback Autónomo (Ejecución Standalone sin API)                |
+-----------------------------------------------------------------------------------+
```

---

## 2. Componentes Principales del Sistema

### 2.1 Motor de Renderizado 3D (Three.js r128)
* **Generación Procedural:** Las escenas, cuadrillas, equipos de construcción (grúas torre, trompos de vaciado, casetas, bombas de concreto) y personajes se construyen geométricamente por código con `THREE.Group`, mallas primitivas optimizadas (`BoxGeometry`, `CylinderGeometry`, `SphereGeometry`) y materiales de sombreado liviano (`MeshLambertMaterial`, `MeshBasicMaterial`).
* **Iluminación Eficiente:** Iluminación ambiental (`THREE.AmbientLight`) combinada con una o dos luces direccionales con sombras precalculadas o proyectadas de bajo consumo, garantizando alto rendimiento gráfico sin ralentizar navegadores estándar.
* **Ciclo de Animación (`requestAnimationFrame`):** Bucle continuo con interpolaciones suaves (*lerp*) para rotaciones orbitales, caminata de personajes y efectos cinemáticos de cámara.

### 2.2 Motor de Audio y Síntesis de Voz
* **Web Speech API:** Invocación controlada de `window.speechSynthesis` con voces en español seleccionadas dinámicamente (`es-ES`, `es-CO`, `es-US`).
* **Ajuste Psicoacústico:** Calibración de tono (`pitch: 0.85`), velocidad (`rate: 0.95`) y volumen (`1.0`) para proyectar un tono sereno, empático y firme acorde a situaciones operativas de obra.
* **Web Audio API:** Síntesis procedural de frecuencias armónicas suaves (campanas tibetanas, ondas senoidales de respiración 4-7-8 y tonos de confirmación) sin depender de archivos de audio externos `.mp3` o `.wav`.

### 2.3 Capa SCORM (Learning Management System Bridge)
* **Detección Jerárquica de API:** El conector busca la interfaz `API` (SCORM 1.2) o `API_1484_11` (SCORM 2004) ascendiendo a través de la jerarquía de ventanas (`window`, `window.parent`, `window.top`, `window.opener`).
* **Gestión de Errores y Modo Autónomo:** Cada llamada a `LMSSetValue` y `LMSCommit` está protegida en bloques `try...catch`. Si la API no responde, el juego redirige el flujo al modo autónomo local sin interrumpir la experiencia formativa del trabajador.

---

## 3. Estructura de Directorios del Repositorio

```text
├── index.html                                 # Portal de acceso unificado (Hub de Juegos)
├── juego1.html                                # Unidad 1: Radio Obra - Canal Limpio
├── juego2.html                                # Unidad 2: El Arquitecto del Tiempo
├── juego3.html                                # Unidad 3: Santuario de Recarga
├── juego4_unidad4.html                        # Unidad 4: La Ruta de tu Quincena 3D
├── juego5_unidad5.html                        # Unidad 5: Voces de Cuadrilla - Cómo me siento
├── README.md                                  # Ficha técnica institucional Seguros Bolívar
├── DOCUMENTACION_SEGUROS_BOLIVAR_LMS.md       # Manual maestro de integración LMS
├── documentacion/                             # Carpeta técnica oficial
│   ├── 01_Requerimientos.md                  # Especificación de requisitos RF / RNF
│   ├── 02_Arquitectura.md                    # Arquitectura técnica de software
│   ├── CORRECCIONES_2026-10-22.md            # Registro histórico de ajustes y refactorizaciones
│   ├── GUIA_INTEGRACION_MOODLE.md            # Instructivo de configuración para administradores Moodle
│   ├── GUIA_PASO_A_PASO_JUEGOS.md            # Guía detallada de mecánicas para el estudiante
│   ├── PREGUNTAS_Y_RESPUESTAS_FAQ.md         # Diagnóstico de incidentes técnicos comunes
│   └── THIRD_PARTY_ASSETS.md                 # Licencias y dependencias de terceros
└── scorm/                                     # Paquetes ZIP listos para distribución
    ├── imsmanifest_juego1.xml                # Manifiestos descriptores SCORM
    ├── imsmanifest_juego2.xml
    ├── imsmanifest_juego3.xml
    ├── imsmanifest_juego4.xml
    ├── imsmanifest_juego5.xml
    ├── Juego_01_RadioObra_SCORM.zip
    ├── Juego_02_ArquitectoTiempo_SCORM.zip
    ├── Juego_03_SantuarioRecarga_SCORM.zip
    ├── Juego_04_SolitarioQuincena_SCORM.zip
    ├── Juego_04_SolitarioQuincena_SCORM2004.zip
    ├── Juego_05_VocesCuadrilla_SCORM.zip
    └── Juego_05_VocesCuadrilla_SCORM2004.zip
```

