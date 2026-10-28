# Guía de Integración, Despliegue y Uso en Plataformas LMS
## Simulaciones Interactivas 3D de Salud Mental y Prevención del Riesgo Psicosocial
### Marco de Referencia: Resolución 2764 de 2022 y Ley 1010 de 2006

Este documento constituye el manual integral para **Administradores de LMS, Diseñadores Instruccionales, Equipos de Seguridad y Salud en el Trabajo (SST), Docentes/Facilitadores y Usuarios Finales (Estudiantes/Trabajadores)** para la instalación, configuración, trazabilidad y aprovechamiento pedagógico de la suite de 5 juegos serios en 3D.

---

## 1. Ficha Técnica y Matriz Pedagógica de los 5 Juegos

Cada juego es un Objeto Virtual de Aprendizaje (OVA) autosuficiente, interactivo y renderizado en tiempo real con WebGL (Three.js), diseñado para ejecutarse tanto de forma autónoma en navegadores web como dentro de cualquier plataforma LMS mediante los estándares **SCORM 1.2** y **SCORM 2004**.

| Unidad / Juego | Título del Recurso | Archivo Fuente | Paquetes SCORM Disponibles | Competencia Clave | Tiempo Estimado | Criterio de Aprobación |
| :--- | :--- | :--- | :--- | :--- | :---: | :---: |
| **Unidad 1** | **Radio Obra: Canal Limpio** | `juego1.html` | `Juego_01_RadioObra_SCORM.zip` | Comunicación asertiva, claridad de rol, prevención del acoso laboral y primeros auxilios psicológicos (PAP). | 15 - 20 min | ≥ 80 / 100 pts |
| **Unidad 2** | **El Arquitecto del Tiempo** | `juego2.html` | `Juego_02_ArquitectoTiempo_SCORM.zip` | Gestión de la carga mental, resolución de órdenes contradictorias y liderazgo preventivo en frentes de obra. | 15 - 20 min | ≥ 80 / 100 pts |
| **Unidad 3** | **Santuario de Recarga** | `juego3.html` | `Juego_03_SantuarioRecarga_SCORM.zip` | Prevención de la fatiga psicofísica, micropausas fisiológicas, desconexión laboral e higiene del sueño reparador. | 15 - 20 min | ≥ 80 / 100 pts |
| **Unidad 4** | **La Ruta de tu Quincena 3D** | `juego4_unidad4.html` | `Juego_04_SolitarioQuincena_SCORM.zip` | Educación financiera preventiva, control del sobreendeudamiento, presupuesto familiar y reducción del estrés financiero. | 15 - 20 min | ≥ 80 / 100 pts |
| **Unidad 5** | **Voces de Cuadrilla: Cómo me siento** | `juego5_unidad5.html` | `Juego_05_VocesCuadrilla_SCORM.zip` | Alfabetización emocional, autorregulación somática en obra y resolución asertiva con soporte en tiempo real. | 20 - 25 min | ≥ 80 / 100 pts |

---

## 2. Guía para Administradores de LMS (Despliegue y Configuración)

### 2.1 Compatibilidad de Plataformas LMS
Los paquetes han sido probados y validados en las principales plataformas de teleformación:
* **Moodle** (v3.9 a v4.4+)
* **Canvas LMS** (Instructure)
* **Blackboard Learn / Ultra**
* **SuccessFactors** (SAP)
* **Totara Learn**
* **Cornerstone OnDemand**
* **D2L Brightspace**
* **Chamilo LMS**

---

### 2.2 Selección del Paquete Adecuado (SCORM 1.2 vs. SCORM 2004)
En el directorio `scorm/` se proporcionan los archivos ZIP empaquetados:
* **SCORM 1.2 (`*_SCORM.zip`):** Recomendado para la gran mayoría de plataformas (Moodle, Chamilo, Totara, Blackboard) por su máxima compatibilidad histórica.
* **SCORM 2004 (`*_SCORM2004.zip`):** Recomendado si su LMS utiliza exclusivamente la 3ª o 4ª edición de SCORM 2004 para almacenar cadenas extendidas de `suspend_data` (> 4096 caracteres) y objetivos avanzados de secuenciación.

---

### 2.3 Parámetros Recomendados de Visualización y Ventana en el LMS

Al crear la actividad SCORM en el curso, configure los siguientes parámetros en la sección de **Apariencia / Ventana**:

| Parámetro LMS | Valor Recomendado | Justificación Técnica |
| :--- | :--- | :--- |
| **Modo de visualización** | **Nueva ventana** (Popup) o **Ventana actual en pantalla completa** | Los entornos 3D requieren el máximo espacio visual posible para permitir una inmersión completa sin barras de desplazamiento innecesarias. |
| **Ancho de ventana** | `100%` o mínimo `1280 px` | El diseño es totalmente fluido y adaptable (responsive). |
| **Alto de ventana** | `100%` o mínimo `800 px` - `900 px` | Garantiza que el canvas 3D y los controles táctiles/inferiores queden visibles simultáneamente. |
| **Permitir redimensionar ventana** | **Sí / Habilitado** | Permite que el usuario maximice la experiencia a su monitor o pantalla. |
| **Permitir barras de desplazamiento** | **Automático / No** | Las simulaciones gestionan internamente su propio scroll en paneles modales. |
| **Permisos de Iframe (si se incrusta)** | `allow="autoplay; camera; microphone; fullscreen; display-capture"` | **Fundamental:** Los juegos utilizan sintetizador de voz (Web Speech API) y aceleración gráfica por hardware. |

---

### 2.4 Configuración de Calificación y Seguimiento en el LMS

Configure la actividad en el módulo de calificaciones de su LMS con las siguientes directrices:

* **Método de calificación:** Puntuación más alta (o primer intento según política institucional).
* **Calificación máxima:** `100 puntos`.
* **Calificación para aprobar (Passing Score):** `80 puntos` (80%).
* **Estado de finalización requerido:** 
  * Marcar como finalizado cuando el estudiante obtenga la calificación de aprobado (**Passed**).
  * O cuando se reporte el estado **Completed**.
* **Intentos múltiples:** Se recomienda habilitar entre **2 y 3 intentos** para permitir el aprendizaje remedial y la práctica de las decisiones correctas.

---

### 2.5 Variables de Comunicación SCORM Implementadas

Los 5 juegos integran el estándar SCORM en su núcleo de JavaScript. A continuación se detallan los elementos de datos transmitidos:

#### SCORM 1.2:
* `cmi.core.lesson_status`: Reporta `"incomplete"` al inicio y pasa a `"passed"` cuando la puntuación es ≥ 80 pts (o `"failed"` si es < 80 pts tras agotar las situaciones).
* `cmi.core.score.raw`: Valor entero entre `0` y `100`.
* `cmi.core.score.min`: Fijado en `0`.
* `cmi.core.score.max`: Fijado en `100`.
* `cmi.core.session_time`: Tiempo real de permanencia y ejecución en formato `HH:MM:SS`.
* `cmi.suspend_data`: Cadena serializada en formato JSON que preserva el estado de avance, estaciones completadas y decisiones previas para reanudar sesiones interrumpidas.
* `cmi.core.exit`: Se establece en `"suspend"` si el usuario sale antes de finalizar, o `""` al completar.

#### SCORM 2004 (en paquetes 2004):
* `cmi.completion_status`: `"incomplete"` / `"completed"`.
* `cmi.success_status`: `"passed"` / `"failed"`.
* `cmi.score.raw`: Puntuación numérica (0 - 100).
* `cmi.score.scaled`: Puntuación normalizada entre `0.0` y `1.0`.
* `cmi.session_time`: Duración en formato ISO 8601 (`PT#H#M#S`).
* `cmi.suspend_data`: Cadena de datos de suspensión.

> [!NOTE]
> Todos los juegos cuentan con **mecanismo de fallback seguro**: si el juego se ejecuta fuera de un LMS (por ejemplo, en un navegador local o intranet web sin API SCORM), el código captura la ausencia del conector sin arrojar errores de consola y permite completar la experiencia formativa al 100%.

---

## 3. Guía Pedagógica y Metodológica (Para Facilitadores y Equipos SST)

### 3.1 Marco Normativo y Enfoque en Prevención del Riesgo Psicosocial
Las simulaciones están alineadas con la legislación colombiana e internacional en seguridad y salud en el trabajo:
* **Resolución 2764 de 2022 (Ministerio del Trabajo):** Adopción de la batería de instrumentos para la evaluación de factores de riesgo psicosocial (intralaboral y extralaboral). Los juegos abordan directamente los dominios de:
  * Demandas del trabajo (carga mental, demandas emocionales, inconsistencia de rol).
  * Control sobre el trabajo (claridad de rol, capacitación, autonomía).
  * Liderazgo y relaciones sociales en el trabajo (comunicación asertiva, apoyo social de compañeros y supervisores).
* **Ley 1010 de 2006:** Prevención, corrección y sanción del acoso laboral y conductas de hostigamiento.
* **Ley 2460 de 2025:** Garantía del derecho a la desconexión laboral efectiva y prevención del tecnoestrés / fatiga psicofísica.

---

### 3.2 Secuencia Didáctica Sugerida (Ruta Formativa)

Se recomienda programar los módulos de forma progresiva a lo largo de un programa de formación de 5 semanas o fases:

```
[Semana 1: Comunicación] ➔ [Semana 2: Carga Mental] ➔ [Semana 3: Autocuidado] ➔ [Semana 4: Bienestar Financiero] ➔ [Semana 5: Inteligencia Emocional]
   Juego 1: Radio Obra        Juego 2: Tiempo           Juego 3: Santuario           Juego 4: Quincena 3D          Juego 5: Voces de Cuadrilla
```

1. **Fase 1 - Comunicación y Convivencia (Juego 1):** Establece las bases del canal limpio y la asertividad entre cuadrilla, supervisores y personal de apoyo.
2. **Fase 2 - Gestión del Tiempo y Priorización (Juego 2):** Entrena al trabajador para jerarquizar órdenes, evitar la sobrecarga y gestionar interrupciones de alto riesgo.
3. **Fase 3 - Prevención de la Fatiga y Descanso (Juego 3):** Fomenta la higiene del sueño, las micropausas y la desconexión real al terminar el turno.
4. **Fase 4 - Tranquilidad y Finanzas Familiares (Juego 4):** Mitiga el estrés extralaboral derivado del sobreendeudamiento mediante la planificación de la quincena.
5. **Fase 5 - Autorregulación Emocional y Apoyo en Terreno (Juego 5):** Consolida la capacidad de identificar emociones somáticas intensas, aplicar técnicas de regulación corporal y buscar apoyo institucional oportuno.

---

## 4. Manual de Operación y Mecánicas de Juego (Para el Usuario Final)

### 4.1 Requisitos Técnicos del Sistema

* **Dispositivos soportados:** Computadores de escritorio, portátiles, tablets y smartphones modernos (Android e iOS).
* **Navegadores recomendados:** Google Chrome (versión 90+), Microsoft Edge (versión 90+), Mozilla Firefox (versión 88+) o Apple Safari (versión 14+).
* **Aceleración por Hardware:** Debe estar activada en el navegador para permitir el renderizado fluido del motor 3D (WebGL).
* **Audio y Parlantes:** Se recomienda utilizar auriculares o altavoces activados para escuchar las respuestas habladas, instrucciones de radio y respiraciones guiadas.

---

### 4.2 Dinámica Particular de Cada Simulación

#### Juego 1: Radio Obra - Canal Limpio
* **Entorno:** Recorrido en primera persona 3D por una losa de construcción en piso 5 con 10 puestos de trabajo.
* **Interacción:** El usuario se desplaza haciendo clic o tocando las estaciones de radio. En cada estación escucha un conflicto o dilema psicosocial en el frente de obra.
* **Toma de Decisiones:** Selecciona la respuesta más asertiva. Las respuestas empáticas y apegadas al protocolo de canal limpio suman puntos; los gritos, agresiones o silencios cómplices restan puntaje y generan retroalimentación correctiva inmediata.

#### Juego 2: El Arquitecto del Tiempo
* **Entorno:** Maqueta isométrica 3D estilo caja interactiva (*bento box*) con rotación de 360 grados.
* **Mecánica:** Se presentan situaciones simultáneas de presión temporal (grúa oscilante, trompo de vaciado de concreto, borde de losa). El usuario debe jerarquizar qué atender primero utilizando la matriz de urgencia vs. importancia sin poner en riesgo la vida ni la salud mental del equipo.

#### Juego 3: Santuario de Recarga
* **Entorno:** 4 estaciones cinematográficas 3D que representan el ciclo completo de recuperación (Caseta de Sombra e Hidratación, Bioseñalizador de Respiración, Casillero de Desconexión de Turno, y Habitación de Sueño Reparador).
* **Mecánica:** 
  * En la estación de respiración, el usuario mantiene presionado el botón al ritmo visual y sonoro 4-7-8 para recuperar su batería fisiológica.
  * En el casillero, marca el checklist de desconexión efectiva para silenciar grupos laborales y guardar los EPP.

#### Juego 4: La Ruta de tu Quincena 3D
* **Entorno:** Tablero 3D interactivo que simula el flujo de ingresos y gastos de la quincena de un trabajador de obra.
* **Mecánica:** El usuario debe clasificar gastos en **Necesidades Básicas**, **Ahorro/Fondo de Emergencia**, **Deudas** y **Gastos Hormiga**. El objetivo es llegar al final de la quincena sin sobreendeudarse ni recurrir a préstamos informales de alto interés.

#### Juego 5: Voces de Cuadrilla - Cómo me siento
* **Entorno:** Escena 3D cinemática en un frente de obra con dos personajes tridimensionales: el trabajador protagonista y el profesional de apoyo (SST/Supervisor).
* **Mecánicas Clave:**
  1. **Lectura de la Situación Crítica:** Se presenta una de las 10 situaciones reales de obra (ej. órdenes opuestas en vaciado de concreto, trabajo nocturno en altura, fatiga acumulada, etc.).
  2. **Reconocimiento Emocional:** El usuario elige entre 6 emociones primarias (Tristeza, Rabia, Miedo, Ansiedad, Desagrado, Alegría), cada una acompañada de su señal somática corporal.
  3. **Resolución Vivencial en 4 Pasos Visuales 3D:**
     * **Paso 1 (Actúa y Respira):** El personaje ejecuta una técnica de regulación corporal en 3D (anillo visual de respiración guiada, soltar hombros, aflojar mandíbula).
     * **Paso 2 (Dilo):** El personaje expresa el guion asertivo con voz natural en español y subtítulos sincronizados.
     * **Paso 3 (Apoyo en Terreno):** El actor de apoyo (SST) camina por la escena 3D, se posiciona junto al trabajador, realiza un gesto de empatía y ofrece una solución institucional real.
     * **Paso 4 (Avanza):** El indicador cambia a resuelto y se habilita el botón para avanzar al siguiente frente.

---

## 5. Preguntas Frecuentes y Solución de Problemas (Troubleshooting)

### 5.1 ¿Qué hacer si no se escucha la voz de los personajes?
* **Causa:** Políticas de seguridad de navegadores modernos que bloquean la reproducción automática de audio (*autoplay*) hasta que el usuario interactúa con la pantalla.
* **Solución:** 
  1. Haga clic o toque cualquier parte de la pantalla del juego para desbloquear el motor de audio.
  2. Verifique que el volumen de la pestaña no esté silenciado.
  3. En todo caso, **todos los diálogos y respuestas cuentan con subtítulos de texto visibles en tiempo real**, por lo que la experiencia de aprendizaje nunca se ve comprometida si el equipo carece de altavoces.

### 5.2 La simulación se ve lenta o la pantalla aparece en negro
* **Causa:** El navegador tiene deshabilitada la aceleración por hardware o los controladores gráficos están desactualizados.
* **Solución:**
  1. En Google Chrome o Microsoft Edge, diríjase a `Configuración` ➔ `Sistema` ➔ active la opción **"Usar aceleración por hardware cuando esté disponible"**.
  2. Reinicie el navegador.

### 5.3 En Moodle / Canvas la ventana del juego se ve cortada o con doble barra de desplazamiento
* **Causa:** La actividad SCORM fue configurada para incrustarse en un marco (*iframe*) de dimensiones estáticas muy reducidas.
* **Solución:** En los ajustes de la actividad SCORM en el LMS, cambie la opción de visualización a **"En una ventana nueva"** con ancho y alto fijados en `100%` o mínimo `1280x840 px`.

### 5.4 El LMS no registra la calificación final del estudiante
* **Causa:** El usuario cerró la pestaña del navegador abruptamente sin hacer clic en el botón final de informe o salida.
* **Solución:** Los juegos envían la instrucción `cmi.core.lesson_status = "passed"` y ejecutan `LMSCommit()` al momento de generar el informe final. Instruya a los usuarios a presionar el botón de **Finalizar y Guardar** antes de cerrar la ventana.

---

## 6. Canales Institucionales de Apoyo

Si durante las simulaciones o en su vida laboral experimenta una situación de sobrecarga emocional, acoso, estrés o fatiga severa, recuerde que su organización cuenta con rutas formales de atención:
* **Área de Seguridad y Salud en el Trabajo (SST) de su empresa.**
* **Comité de Convivencia Laboral.**
* **Línea de Orientación y Apoyo Psicosocial institucional (confidencial y gratuita).**

