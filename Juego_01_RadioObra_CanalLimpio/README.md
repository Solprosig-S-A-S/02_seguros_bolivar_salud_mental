# Canal Limpio: Aventura 3D en Piso 5
### Videojuego 3D en 1ª Persona Mobile-First con Diálogos Flotantes y Opciones Táctiles
**Programa de Salud Mental y Prevención del Riesgo Psicosocial en Construcción**  
*Seguros Bolívar / ARL Bolívar - Unidad 1: Comunicación Asertiva y Clima de Cuadrilla*

---

## 1. Ficha Técnica

| Parámetro | Detalle |
| :--- | :--- |
| **Motor Gráfico** | 3D Real en WebGL (Three.js r128) optimizado para dispositivos móviles Android. |
| **Perspectiva** | Primera persona (1ª persona) vertical (Mobile-First 9:16). |
| **Sistema de Diálogos** | **Bocadillos proyectados directamente sobre los personajes 3D** con cola direccional y efecto pop sonoro. |
| **Mecánica de Movimiento** | **Caminata 3D Real con un solo botón:** Al pulsar `AVANZAR`, la cámara se traslada suavemente en el espacio 3D con bamboleo (*head bobbing* sinusoidal) y sonido de pisadas en concreto sincronizado. |
| **Consola de Respuestas** | **Interfaz limpia:** El usuario solo ve las tarjetas táctiles de decisión (A, B, C) y el botón de avance, sin textos duplicados. |
| **Arquitectura** | **Single-File Self-Contained (`index.html`)**: HTML5 + CSS3 + Three.js + Web Audio API + SCORM inline. |
| **Estándar e-Learning** | SCORM 1.2 / 2004 con nota mínima de aprobación del **80%**. |

---

## 2. Entorno 3D y las 4 Estaciones Operativas

1. **Estación 1 (Columna de Relevo):**
   - El Residente de Obra habla mediante un bocadillo que flota directamente sobre la columna y la bitácora: *"¡Atención cuadrilla! Relevo de turno en la columna: completen la bitácora..."*.
   - *Enfoque:* Todo relevo debe registrar **Material**, **Cantidad exacta** y **Ubicación verificada** (*Res. 2764 de 2022*), eliminando la fatiga por ambigüedad.

2. **Estación 2 (Caminata al Pasillo y Radio en Mano):**
   - El jugador camina hacia el pasillo; el radioteléfono 3D emite un bocadillo de alerta con borde rojo: *"¡Suba ligero esos parales a la torre B o los echan a todos!"*.
   - *Enfoque:* Técnica **"Repetir para Validar"**, exigiendo respeto profesional sin contraatacar ni someterse (*Ley 1010 de 2006*).

3. **Estación 3 (Caminata a la Zona de Izaje y Cuadrilla):**
   - El Maestro y el Carpintero discuten bajo la carga suspendida de la grúa torre con bocadillos de tensión.
   - *Enfoque:* Detener la maniobra, unificar el canal y respaldar al compañero vulnerable (*Res. 2764 de 2022 - Apoyo Social*).

4. **Estación 4 (Caminata al Borde Perimetral y Baranda Suelta):**
   - En el borde del piso 5, un compañero susurra: *"Ojo con esa baranda suelta, pero no diga nada para no frenar la jornada..."*.
   - *Enfoque:* Vencer el miedo a represalias, capturar la foto de evidencia (con flash y obturador) y emitir el reporte preventivo a SST.

5. **Estación 5 (Cierre de Jornada y Debrief de Cuadrilla):**
   - La cámara camina de vuelta al centro del Piso 5 frente a la cuadrilla reunida (Residente, Inspector SISO y Maestro) con la ciudad al atardecer de fondo.
   - Transmisión por radio y bocadillo 3D con fanfarria armónica (*playDebriefChime*): *"¡Atención cuadrilla! Baranda asegurada, maniobras coordinadas y bitácora al día. ¡Jornada concluida con éxito!"*.
   - **Balance Integral de Salud Mental:** Dashboard con los 4 pilares formativos (Claridad de Rol, Filtro Asertivo, Apoyo Social y Seguridad Psicológica).
   - **Cierre Operativo y SCORM:** Registro automatizado de nota y estado (`cmi.core.score.raw` y `cmi.core.lesson_status`), opción de repasar/reintentar y pantalla de despedida con confirmación de guardado.

---

## 3. Archivos del Paquete SCORM

```text
Juego_01_RadioObra_CanalLimpio/
├── index.html                      # Videojuego 3D 100% autocontenido (WebGL + Pasos + Diálogos 3D + SCORM)
├── imsmanifest.xml                 # Manifiesto oficial SCORM 1.2 (80% masteryscore)
├── Juego_01_RadioObra_SCORM.zip     # Paquete ZIP listo para subir al LMS
└── README.md                       # Documentación técnica y pedagógica completa
```
