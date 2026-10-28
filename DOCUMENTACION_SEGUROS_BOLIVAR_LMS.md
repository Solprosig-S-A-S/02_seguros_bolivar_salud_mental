# Manual Exclusivo de Operación y Despliegue en Plataforma LMS
## Suite de Juegos Serios 3D - Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Gerencia de Prevención y Seguridad y Salud en el Trabajo (SST)
#### Marco Normativo: Resolución 2764 de 2022 • Ley 1010 de 2006 • Ley 2460 de 2025

---

## 1. Presentación Institucional y Objetivos del Proyecto

El presente manual es de uso exclusivo para los equipos de **Tecnología Educativa, Administradores LMS, Diseñadores Instruccionales, Consultores de Prevención y Profesionales SST de Seguros Bolívar ARL** encargados de implementar, operar, monitorear y evaluar la suite de 5 experiencias gamificadas en 3D en la plataforma de aprendizaje institucional (Moodle Bolívar / Campus Virtual Seguros Bolívar) o en los sistemas de formación de las empresas cliente afiliadas a la ARL.

### 1.1 Propósito
Fortalecer las competencias psicosociales de los trabajadores y contratistas en frentes de trabajo de alto riesgo (especialmente en el sector de la construcción y afines), mediante simulaciones interactivas en tiempo real desarrolladas con Three.js, empaquetadas bajo el estándar SCORM (1.2 y 2004) y alineadas a los lineamientos de la **Batería de Instrumentos para la Evaluación de Factores de Riesgo Psicosocial (Resolución 2764 de 2022)**.

### 1.2 Canales Institucionales de Apoyo Seguros Bolívar
En todas las experiencias se promueve de forma activa el uso de los canales formales de atención que Seguros Bolívar dispone para sus empresas afiliadas y trabajadores:
* **Línea de Atención Psicosocial y Salud Mental Seguros Bolívar** (Asistencia psicológica gratuita, confidencial y 24/7).
* **Canales de Asesoría Técnica en Prevención SST de Seguros Bolívar ARL**.
* **Comités de Convivencia Laboral de las empresas afiliadas**.

---

## 2. Ficha Técnica y Matriz Pedagógica de los 5 Módulos

| Unidad / Juego | Nombre Oficial | Archivo HTML | Paquetes SCORM | Dimensión del Riesgo Psicosocial (Res. 2764) | Mecánica Principal | Tiempo Estimado | Puntuación Mínima |
| :--- | :--- | :--- | :--- | :--- | :--- | :---: | :---: |
| **Unidad 1** | **Radio Obra: Canal Limpio** | `juego1.html` | `scorm/Juego_01_RadioObra_SCORM.zip` | Liderazgo y relaciones sociales en el trabajo, claridad de rol y prevención del acoso laboral (Ley 1010). | Aventura 3D en 1ª persona; recorrido por 10 puestos en losa piso 5 con toma de decisiones de comunicación asertiva. | 15 - 20 min | 80 / 100 |
| **Unidad 2** | **El Arquitecto del Tiempo** | `juego2.html` | `scorm/Juego_02_ArquitectoTiempo_SCORM.zip` | Demandas del trabajo: carga mental, ritmo de trabajo y ambigüedad / conflicto de órdenes. | Maqueta isométrica 3D (*bento box*); resolución de prioridades urgentes vs importantes con semáforo de sobrecarga. | 15 - 20 min | 80 / 100 |
| **Unidad 3** | **Santuario de Recarga** | `juego3.html` | `scorm/Juego_03_SantuarioRecarga_SCORM.zip` | Prevención de la fatiga psicofísica, micropausas somáticas y desconexión laboral efectiva (Ley 2460). | 4 estaciones 3D: caseta de sombra, bioseñalizador de respiración 4-7-8, casillero de desconexión y habitación de descanso nocturno. | 15 - 20 min | 80 / 100 |
| **Unidad 4** | **La Ruta de tu Quincena 3D** | `juego4_unidad4.html` | `scorm/Juego_04_SolitarioQuincena_SCORM.zip`<br>`scorm/Juego_04_SolitarioQuincena_SCORM2004.zip` | Factores extralaborales: economía familiar, control del sobreendeudamiento y prevención de créditos informales. | Tablero 3D interactivo; distribución de ingresos en necesidades, deudas, imprevistos y descarte de gastos hormiga. | 15 - 20 min | 80 / 100 |
| **Unidad 5** | **Voces de Cuadrilla: Cómo me siento** | `juego5_unidad5.html` | `scorm/Juego_05_VocesCuadrilla_SCORM.zip`<br>`scorm/Juego_05_VocesCuadrilla_SCORM2004.zip` | Demandas emocionales del puesto, autorregulación somática en caliente y resolución asertiva en terreno. | 10 situaciones de obra reales; reconocimiento emocional somático y secuencia vivencial 3D con doble personaje (trabajador + SST). | 20 - 25 min | 80 / 100 |

---

## 3. Guía Paso a Paso para el Administrador del LMS

### 3.1 Carga del Paquete en Moodle (Campus Virtual Seguros Bolívar)
1. Ingrese con rol de **Administrador / Profesor Editor** en el curso correspondiente de Salud Mental.
2. Active el modo de edición (botón superior derecho).
3. Seleccione el módulo o semana donde desea incorporar el juego y haga clic en **+ Añadir una actividad o un recurso**.
4. Seleccione **Paquete SCORM**.
5. Diligencie los campos obligatorios:
   * **Nombre:** Ingrese el nombre formal (ej. `Módulo 5: Simulación 3D - Voces de Cuadrilla`).
   * **Descripción:** Breve resumen de la competencia y recordatorio de usar auriculares o altavoces.
6. En la sección **Paquete**, arrastre y suelte el archivo correspondiente desde la carpeta `scorm/` (ej. `Juego_05_VocesCuadrilla_SCORM.zip`).

---

### 3.2 Parámetros Exactos de Configuración en Moodle

Para garantizar la correcta ejecución del motor gráfico Three.js y el registro preciso de notas, aplique la siguiente configuración:

#### A. Sección "Apariencia"
* **Mostrar paquete:** Seleccione **En una ventana nueva**.
* **Ancho de la ventana:** `100%` (o mínimo `1280 px`).
* **Alto de la ventana:** `100%` (o mínimo `840 px`).
* **Permitir que la ventana sea redimensionada:** `Sí`.
* **Mostrar barra de menú / de estado / de herramientas:** `No`.
* **Visualizar estructura del curso en la página de entrada:** `No`.
* **Ocultar botones de navegación SCORM:** `Sí` (el juego cuenta con su propio flujo de navegación interno).

#### B. Sección "Disponibilidad" y "Calificación"
* **Método de calificación:** `Calificación más alta` (o `Primer intento` según lineamiento corporativo).
* **Calificación máxima:** `100`.
* **Calificación para aprobar (Aprobación):** `80`.

#### C. Sección "Intentos"
* **Número de intentos:** Se recomienda configurar **3 intentos**. Esto permite que el trabajador, en caso de fallar en una primera aproximación reflexiva, pueda repetir la experiencia y consolidar la conducta preventiva deseada.
* **Calificación de los intentos:** `Calificación más alta`.

#### D. Sección "Finalización de Actividad"
* **Rastreo de finalización:** `Mostrar la actividad como completada cuando se cumplan las condiciones`.
* **Condiciones requeridas:**
  * Marcar `El estudiante debe recibir una calificación para completar esta actividad`.
  * Marcar `El estudiante debe recibir una calificación de aprobado para completar esta actividad`.
  * Estado de finalización: `passed` / `completed`.

---

### 3.3 Parámetros para otros LMS (Canvas, Blackboard, SuccessFactors)
* **Canvas LMS:** Suba el paquete mediante la herramienta **SCORM** del menú del curso. Seleccione el tipo de asignación como **Graded Assignment** con puntuación de 100 puntos y configure la opción de lanzamiento en **Load in a new tab** (Abrir en pestaña nueva).
* **Blackboard Ultra / Learn:** Cree un elemento de contenido SCORM, asigne calificación basada en SCORM `cmi.core.score.raw` con peso de 100 pts y active la casilla de visualización **Open in new window**.
* **SAP SuccessFactors:** Importe el ZIP en el catálogo de contenidos (`Content > Import Content`), configure el launch type como `Player (New Window)` con dimensiones `Width=1280, Height=850, Resizable=True`.

---

## 4. Trazabilidad Técnica y Modelo de Datos SCORM

Los 5 juegos utilizan un envoltorio nativo desarrollado específicamente para interactuar sin librerías externas con la API SCORM (`API` para SCORM 1.2 o `API_1484_11` para SCORM 2004).

### 4.1 Variables SCORM 1.2 Transmitidas:
```javascript
// Al iniciar la simulación:
LMSInitialize("");
LMSSetValue("cmi.core.lesson_status", "incomplete");
LMSCommit("");

// Durante la simulación (guardado de estado parcial):
LMSSetValue("cmi.suspend_data", JSON.stringify({ currentSituation: 3, score: 75, history: [...] }));
LMSSetValue("cmi.core.exit", "suspend");
LMSCommit("");

// Al completar la evaluación final:
LMSSetValue("cmi.core.score.raw", finalScore);        // Valor entre 0 y 100
LMSSetValue("cmi.core.score.min", "0");
LMSSetValue("cmi.core.score.max", "100");
LMSSetValue("cmi.core.session_time", formattedTime);   // Formato HH:MM:SS
LMSSetValue("cmi.core.lesson_status", finalScore >= 80 ? "passed" : "failed");
LMSSetValue("cmi.core.exit", "");
LMSCommit("");
LMSFinish("");
```

### 4.2 Mecanismo de Fallback Seguro (Modo Autónomo)
Si un consultor de Seguros Bolívar o una empresa cliente abre los archivos directamente desde un enlace web, portal intranet o repositorio local sin plataforma LMS:
* El script detecta de forma transparente la ausencia de la API (`window.API == null`).
* El juego **continúa operando al 100% de sus capacidades gráficas, de audio y pedagógicas**.
* Los puntajes y diagnósticos se calculan y presentan visualmente en pantalla en un informe detallado con botón para descargar o imprimir el resumen en PDF, sin generar bloqueos ni errores en la consola del navegador.

---

## 5. Arquitectura Técnica y Requisitos de Infraestructura

### 5.1 Especificaciones de Software
* **Motor 3D:** Three.js (r128). Todos los modelos, geometrías, luces y partículas se compilan en tiempo de ejecución sin requerir pesados archivos binarios `.gltf` o `.fbx` externos, garantizando tiempos de carga inferiores a 2 segundos en redes corporativas de obra.
* **Tipografía:** *Plus Jakarta Sans* integrada de forma fluida con fallbacks seguros del sistema (`system-ui`, `Segoe UI`, `Roboto`).
* **Iconografía:** **100% vector SVG nativo**. Cumple con el estándar corporativo de Seguros Bolívar: cero emojis informales de mensajería, asegurando una presentación sobria y altamente profesional.
* **Audio y Voz:** Integración nativa con **Web Speech API** (`speechSynthesis`), configurada con voces en español de tono natural masculino (`pitch: 0.85`, `rate: 0.95`). Se complementa obligatoriamente con subtítulos dinámicos de alto contraste en pantalla para accesibilidad total (WCAG 2.1 AA).

### 5.2 Requerimientos Mínimos de Hardware y Conectividad
* **Dispositivos:** Computadores de escritorio corporativos, portátiles, tablets rugerizadas y dispositivos móviles de operarios (Android 9+ o iOS 13+).
* **Navegadores Soportados:** 
  * Google Chrome / Edge Chromium (versión 90 o superior) - *Altamente recomendado*.
  * Mozilla Firefox (versión 88 o superior).
  * Apple Safari (versión 14 o superior).
* **Aceleración por Hardware:** Requiere soporte de WebGL 1.0 / 2.0 activo en el navegador.
* **Ancho de Banda:** Consumo mínimo de datos (< 500 KB por juego tras la primera carga en caché), ideal para conexiones en campamentos de obra y zonas periféricas.

---

## 6. Dinámica Operativa para Facilitadores y Docentes de Seguros Bolívar

### 6.1 Cómo Conducir una Sesión de Aprendizaje
Los profesionales de prevención de Seguros Bolívar pueden utilizar estos juegos bajo dos modalidades:

1. **Modalidad Asincrónica (Autoformación):**
   * El trabajador ingresa a su propio ritmo a la plataforma LMS.
   * Completa la simulación y genera su certificado o registro de cumplimiento con nota ≥ 80 pts.
2. **Modalidad Sincrónica / Taller de Liderazgo y SST en Obra:**
   * El facilitador proyecta el juego en pantalla grande o sala de capacitación del campamento.
   * Plantea las situaciones críticas a la cuadrilla y genera debates participativos: *¿Qué emoción sentimos aquí? ¿Por qué la rabia o el miedo pueden causar un accidente en este vaciado?*
   * Se evalúa en consenso la mejor respuesta asertiva y se observa en la maqueta 3D la reacción del personaje y el acompañamiento del profesional SST.

---

## 7. Solución de Problemas Frecuentes (Troubleshooting)

### P1: La voz de los personajes no se reproduce automáticamente.
* **Diagnóstico:** Políticas de seguridad del navegador impiden el *autoplay* de audio antes de la primera interacción voluntaria del usuario.
* **Solución:** 
  1. El trabajador debe hacer clic o tocar la pantalla en cualquier parte al ingresar al juego.
  2. Verificar que los permisos de sonido del sitio no estén en "Silenciar".
  3. Indicar al trabajador que los subtítulos en pantalla muestran exactamente cada palabra dicha, por lo que la actividad puede completarse aún en ambientes ruidosos de obra sin altavoces.

### P2: El juego se visualiza con franjas negras o muy pequeño dentro de Moodle.
* **Diagnóstico:** La actividad fue configurada con el parámetro "En la misma ventana" dentro de un iframe limitado.
* **Solución:** Modifique la configuración del SCORM en Moodle: en la sección **Apariencia**, seleccione **En una ventana nueva** con dimensiones `100% x 100%` o `1280 x 840 px`.

### P3: El rendimiento gráfico es lento o con saltos de fotogramas (lag).
* **Diagnóstico:** La aceleración por hardware del navegador del usuario está desactivada.
* **Solución:** En Chrome o Edge, vaya a `Configuración > Sistema > Usar aceleración por hardware cuando esté disponible` y asegúrese de que esté activada. Luego reinicie el navegador.

### P4: El estudiante completó el juego pero la nota no aparece en el libro de calificaciones.
* **Diagnóstico:** El estudiante cerró la ventana antes de llegar a la pantalla final de diagnóstico o cerró la pestaña sin permitir la ejecución de `LMSCommit()`.
* **Solución:** Recordar a los trabajadores en las instrucciones iniciales que deben pulsar el botón de **"Ver Informe Final"** o **"Finalizar Evaluación"** al término de la última situación para que el LMS registre formalmente el estado `passed`.

---

## 8. Soporte y Contacto Técnico Especializado

Para inquietudes técnicas adicionales sobre empaquetamiento SCORM, personalización de frentes de obra o ajustes de la plataforma LMS:
* **Equipo de Desarrollo y Tecnología Educativa:** Consulte el repositorio central de código en Git y la carpeta `documentacion/`.
* **Gerencia de Prevención y Riesgo Psicosocial - Seguros Bolívar ARL.**

