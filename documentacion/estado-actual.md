# Estado y arquitectura

Fecha de referencia: 22 de octubre de 2026.

## Archivos principales

| Archivo | Función |
| --- | --- |
| `index.html` | Portal: enlaces directos, juegos embebidos en iframe y descarga de paquetes SCORM. Acepta `?game=1`, `?game=2` y `?game=3`. |
| `juego1.html` | Canal Limpio / Operación Piso 5. |
| `juego2.html` | El Arquitecto del Tiempo. |
| `juego3.html` | Santuario de Recarga. |
| `scorm/` | Tres ZIP para LMS y tres manifiestos XML de referencia. |
| `scratch/` | Utilidades locales de análisis y validación; carpeta excluida de Git. |

## Base técnica

Cada juego es un HTML independiente con estilos y JavaScript integrados. No hay un proceso de compilación ni módulos compartidos. Usan Three.js r128 desde CDN, fuentes de Google Fonts, WebGL y audio procedural mediante Web Audio API.

Los motores construyen escenas con geometría y materiales de Three.js, animan con `requestAnimationFrame` y atienden controles de puntero y cambios de tamaño. La interfaz está orientada a interacción táctil y utiliza paneles superpuestos al escenario.

Cada archivo contiene su propio adaptador `ScormAPI`, motor de sonido, motor 3D y controlador narrativo. Los cambios comunes deben revisarse por separado en los tres archivos.

## Juego 1: Canal Limpio

- Controlador: `AdventureGame`; motor: `Real3DEngine`; narración: `VoiceEngine`.
- Recorrido de cámara en primera persona entre diez estaciones, con mirada mediante arrastre, respuestas en bocadillos y retroalimentación pedagógica.
- Temas: bitácora y claridad de rol, comunicación por radio, coordinación de izaje, reporte de baranda dañada, coacción laboral, fatiga, primeros auxilios psicológicos, intervención ante descoordinación motora, integridad de ensayos y desescalamiento de conflictos.
- Cada acierto suma 10 puntos; se aprueba desde 80/100. Al terminar hay una asamblea de cierre y un informe según el resultado global.
- Incluye audio MP3 embebido para parte de la narración y síntesis de voz del navegador como alternativa.
- Adaptador para SCORM 1.2 y 2004; en modo local registra puntuación y estado simulados en `localStorage`.

## Juego 2: El Arquitecto del Tiempo

- Controlador: `GameApp`; motor: `Isometric3DEngine`.
- Cuatro rondas en un escenario isométrico: vaciado con órdenes cruzadas, grúa ante viento, borde perimetral al cierre y pasillo bloqueado durante el relevo.
- Tres respuestas por ronda, consecuencias animadas y panel de retroalimentación antes de avanzar.
- Cada acierto suma 25 puntos; se aprueba desde 75/100, también en el manifiesto SCORM.
- La carga mental comienza en 30; un acierto resta 15 con mínimo de 15 y un error suma 25 con máximo de 100. El semáforo indica enfocado hasta 35, alerta hasta 70 y sobrecarga por encima de 70.
- Informe y escena final de éxito o fracaso. Adaptador SCORM 1.2.

## Juego 3: Santuario de Recarga

- Controlador: `GameApp`; motor: `Santuario3DEngine`; confeti: `Confetti2D`.
- Cuatro estaciones consecutivas: entrar a la caseta y beber agua; mantener pulsado un círculo durante tres ciclos respiratorios 4-7-8; completar cuatro acciones del casillero; completar tres acciones del dormitorio.
- Hay desplazamiento del avatar y colisiones, transiciones de cámara, cambios de luz, efecto visual de fatiga y animaciones específicas de cada estación.
- Cada estación completa suma 25 puntos. La batería comienza en 15% y pasa a 40%, 65%, 85% y 100%.
- La respiración requiere 57 segundos efectivos para tres ciclos completos. Al soltar se conserva el número de ciclos terminados y se reinicia el ciclo en curso.
- La retroalimentación permite avanzar manualmente o tras 4,5 segundos. El éxito activa celebración 3D, confeti, batería animada y sellos antes del informe.
- El umbral programado es 75/100, aunque el recorrido normal exige completar las cuatro estaciones y termina con 100. Adaptador SCORM 1.2.

## Distribución y persistencia

Cada ZIP contiene `imsmanifest.xml` e `index.html`; este último debe ser una copia exacta del HTML del juego correspondiente, no del portal. Tras modificar un juego o su manifiesto se debe regenerar su paquete y comprobar su contenido.

Los paquetes mantienen las dependencias de red del HTML. No hay servidor de aplicación ni base de datos propios. Los adaptadores envían puntuación y estado al LMS; no se implementa recuperación del punto de avance mediante `suspend_data` o `lesson_location`.
