# El Arquitecto del Tiempo: Carga Mental y Toma de Decisiones en Obra
### Videojuego 3D Isométrico Mobile-First con Semáforo de Carga Mental y Respuestas Concretas
**Programa de Salud Mental y Prevención del Riesgo Psicosocial en Construcción**  
*Seguros Bolívar / ARL Bolívar - Unidad 2: Gestión de la Carga Mental y Priorización Operativa*

---

## 1. Ficha Técnica

| Parámetro | Detalle |
| :--- | :--- |
| **Motor Gráfico** | Three.js (WebGL r128) optimizado para navegadores móviles a 60 fps estables en formato Bento Box isométrico 3D. |
| **Perspectiva** | Isométrica 3/4 aérea con frentes activos de trabajo y rotación táctil 360° optimizada para pulgar. |
| **Diseño Responsive** | Vertical Mobile-First (máximo 430px centrado en PC, 100% en pantallas móviles). |
| **Medidor de Carga Mental** | Semáforo de carga mental en cabecera: Verde (Enfocado 15%-35%) → Amarillo (Alerta 36%-70%) → Rojo (Sobrecarga > 70%). |
| **Toma de Decisiones** | 3 opciones narrativas concretas y comprensibles por ronda (A, B, C) con orden alternado para evitar patrones mecánicos. |
| **Bocadillos 3D** | Diálogo proyectado en tiempo real sobre los personajes en la losa según el frente de obra activo. |
| **Retroalimentación** | Drawer inferior formativo limpio y conciso: un solo párrafo claro con fundamentación en la *Resolución 2764 de 2022*. |
| **Efectos y Audio** | Sintetizador procedural Web Audio API (acierto armónico, alerta de sobrecarga y marcha de victoria) sin archivos externos. |
| **Iconografía** | 100% Vectores SVG geométricos en línea (cero emojis Unicode). |
| **Estándar e-Learning** | SCORM 1.2 autocontenido con nota de aprobación del **80%** (25 pts por acierto, total 100 pts). |

---

## 2. Las 4 Rondas Pedagógicas de Gestión de la Carga Mental

1. **Ronda 1: Claridad de Mando vs Sobrecarga por Ambigüedad (Frente 1: Vaciado de Concreto)**
   - *Situación:* Dos supervisores dan instrucciones contradictorias sobre el vaciado del concreto al mismo tiempo.
   - *Decisión Correcta (B):* Pausar el mixer 3 minutos y unificar el mando oficial en planilla antes de verter.
   - *Fundamento:* Aclarar el rol y la prioridad de mando antes de ejecutar previene la sobrecarga por ambigüedad y elimina costosos reprocesos de demolición (*Res. 2764 de 2022*).

2. **Ronda 2: Gestión de Imprevistos Críticos en Altura (Frente 2: Grúa Torre y Formaleta)**
   - *Situación:* Ráfagas de viento imprevistas y alerta mecánica en el motor de la grúa mientras traslada una formaleta metálica.
   - *Decisión Correcta (A):* ¡Parar la maniobra ya mismo y evacuar el radio a 10 metros!
   - *Fundamento:* Detener la maniobra y acordonar el radio de caída es prioritario. En emergencias, la protección de la vida prima sobre cualquier meta de cronograma.

3. **Ronda 3: El Dilema del Afán al Cierre (Frente 3: Borde Perimetral y Parales)**
   - *Situación:* Faltan 10 minutos para el fin del turno y la baranda perimetral de parales quedó a medio ajustar.
   - *Decisión Correcta (C):* Reorganizar calmadamente y señalizar a 2 metros con cinta reflectiva, coordinando la entrega en bitácora al relevo.
   - *Fundamento:* El 60% de los accidentes graves ocurren en los últimos 30 minutos de turno por fatiga y prisa desordenada. La entrega técnica y serena salva vidas.

4. **Ronda 4: Orden, Aseo y Clima de Relevo (Frente 4: Pasillo Central y Acopio)**
   - *Situación:* Pasillo principal de evacuación bloqueado con escombros, tablas con puntillas y carretillas al terminar el vaciado.
   - *Decisión Correcta (B):* Convocar 10 minutos de orden y aseo colectivo con toda la cuadrilla antes de salir.
   - *Fundamento:* Un entorno de trabajo limpio y despejado disminuye la fatiga visual, previene tropiezos y fomenta el respeto mutuo entre turnos.

---

## 3. Estructura de Archivos del Paquete SCORM

```text
Juego_02_ArquitectoTiempo_CargaMental/
├── index.html                           # Juego 3D Isométrico autocontenido
├── imsmanifest.xml                      # Manifiesto oficial SCORM 1.2 (masteryscore 80)
├── Juego_02_ArquitectoTiempo_SCORM.zip  # Paquete ZIP listo para subir a la plataforma LMS
└── README.md                            # Documentación técnica y pedagógica
```
