# Experiencias Gamificadas de Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Resolución 2764 de 2022 y Ley 1010 de 2006

Repositorio de simulaciones interactivas en 3D desarrolladas con **Three.js**, listas para su despliegue inmediato en **GitHub Pages** y empaquetadas como Objetos Virtuales de Aprendizaje compatibles con **SCORM 1.2** para plataformas LMS empresariales.

Documentación técnica inicial y pendientes: [documentacion/README.md](documentacion/README.md). Esta carpeta se actualizará únicamente cuando el usuario lo solicite.

---

## 🌐 Acceso en GitHub Pages

Al habilitar **GitHub Pages** en la rama `main` (directorio `/root`), la plataforma queda publicada y navegable:

* **Portal Principal (Hub de Selección):** [`index.html`](file:///./index.html)
* **Juego 01 (Canal Limpio en Primera Persona):** [`juego1.html`](file:///./juego1.html)
* **Juego 02 (El Arquitecto del Tiempo Isométrico):** [`juego2.html`](file:///./juego2.html)
* **Juego 03 (Santuario de Recarga en 3D Integrado):** [`juego3.html`](file:///./juego3.html)

---

## 🎮 Contenido del Repositorio

### 1. [Juego 01: Radio Obra - Canal Limpio](file:///./juego1.html)
* **Archivo:** `juego1.html`
* **Formato:** Aventura en Primera Persona 3D con navegación peatonal cinemática y rotación libre táctil 360°.
* **Enfoque Psicosocial:** Comunicación asertiva, claridad de rol, prevención del acoso laboral (Ley 1010 de 2006), primeros auxilios psicológicos (PAP) y desescalamiento de crisis colectiva.
* **Mecánica:** Desplazamiento por 10 estaciones de trabajo realistas en losa de piso 5, interacción con cuadrilla mediante bocadillos proyectados en 3D, y toma de decisiones éticas con consecuencias visibles en el entorno.
* **Paquete SCORM:** `scorm/Juego_01_RadioObra_SCORM.zip`

### 2. [Juego 02: El Arquitecto del Tiempo - Carga Mental](file:///./juego2.html)
* **Archivo:** `juego2.html`
* **Formato:** Simulación Isométrica 3D estilo *Bento Box* con rotación orbital e iluminación direccional.
* **Enfoque Psicosocial:** Gestión de la carga mental y sobrecarga cognitiva, ambigüedad/conflicto de órdenes, liderazgo preventivo y relaciones interpersonales en obra.
* **Mecánica:** 
  * 4 frentes críticos con animación concreta en tiempo real (trompo mezclador, grúa torre con carga oscilante por viento, borde perimetral a 18 m y pasillo central de relevo).
  * **Consola de Decisión Directa:** Opciones compactas con evaluación inmediata, manteniendo despejado más del 75% del visor 3D para apreciar la simulación.
  * Semáforo dinámico de Carga Mental (Enfocado, Alerta, Sobrecarga).
* **Paquete SCORM:** `scorm/Juego_02_ArquitectoTiempo_SCORM.zip`

### 3. [Juego 03: Santuario de Recarga - Fatiga y Desconexión Laboral](file:///./juego3.html)
* **Archivo:** `juego3.html`
* **Formato:** Simulación 3D interactiva con transiciones de cámara cinematográficas, efectos dinámicos de cansancio visual (*Depth of Field*) y ciclo lumínico cronobiológico (mediodía -> atardecer -> noche -> amanecer triunfal).
* **Enfoque Psicosocial:** Prevención de la fatiga psicofísica, autorregulación del estrés mediante micropausas fisiológicas, derecho a la desconexión laboral (Ley 2460 de 2025) e higiene del sueño reparador para personal de alto riesgo (Clase V, Res. 2764 de 2022).
* **Mecánica:**
  * **Estación 1 (Caseta de Sombra e Hidratación):** Desplazamiento hacia la carpa protegida del sol; al hidratarse se disipa el desenfoque y temblor visual de fatiga.
  * **Estación 2 (El Bioseñalizador 3D):** Vista en primer plano a la radio de obra; respiración guiada con ritmo 4-7-8 manteniendo pulsado el botón táctil con retroalimentación sonora armónica.
  * **Estación 3 (El Casillero de Desconexión):** Vestidores al atardecer; checklist interactivo para guardar casco, botas, silenciar notificaciones y asegurar el candado con animación 3D de la puerta.
  * **Estación 4 (Espacio de Descanso Nocturno):** Habitación nocturna; apagado de luz azul en el móvil, cierre de cortinas y apagado de velador para optimizar melatonina.
  * **Finales y Batería Vital:** 2 desenlaces según el nivel de recarga. El final exitoso es una **celebración cinemática**: amanecer 3D con podio dorado, trabajador festejando, batería gigante que se carga, fuegos artificiales, confeti 3D/2D, fanfarria y sellos de logro, seguido del informe de diagnóstico; el final fallido muestra el déficit de descanso con plan remedial.
* **Paquete SCORM:** `scorm/Juego_03_SantuarioRecarga_SCORM.zip`

---

## 📂 Estructura Limpia del Repositorio

```text
├── index.html        # Portal unificado para GitHub Pages
├── juego1.html       # Juego 01: Canal Limpio (Aventura en 1ª Persona 3D)
├── juego2.html       # Juego 02: El Arquitecto del Tiempo (Isométrico 3D)
├── juego3.html       # Juego 03: Santuario de Recarga (3D Integrado de Autocuidado)
├── scorm/            # Paquetes y manifiestos SCORM 1.2 listos para LMS
│   ├── Juego_01_RadioObra_SCORM.zip
│   ├── Juego_02_ArquitectoTiempo_SCORM.zip
│   ├── Juego_03_SantuarioRecarga_SCORM.zip
│   ├── imsmanifest_juego1.xml
│   ├── imsmanifest_juego2.xml
│   └── imsmanifest_juego3.xml
├── README.md         # Documentación técnica y pedagógica
└── .gitignore        # Exclusiones de control de versiones
```

---

## 🛠️ Especificaciones Técnicas

* **Motor Gráfico:** Three.js (r128) nativo sin dependencias de compilación externa.
* **Estilo Visual:** Paleta corporativa Seguros Bolívar (azul marino `#023047`, amarillo `#FFB703`, verde azulado `#2A9D8F`), tipografía fluida *Plus Jakarta Sans* y superficies translúcidas con *glassmorphism* (`backdrop-filter`).
* **Iconografía:** 100% vector SVG nativo (0 emojis, apto para entornos corporativos e institucionales).
* **Compatibilidad:** Responsive design adaptado a pantallas táctiles móviles, tabletas y computadores de escritorio.
* **Estándar SCORM:** SCORM 1.2 (`LMSInitialize`, `LMSSetValue`, `LMSCommit`, `LMSFinish`) con soporte de ejecución autónoma (fallback seguro cuando no se detecta API LMS).

---

## 📄 Licencia y Derechos

Desarrollado para **Seguros Bolívar ARL**. Todos los derechos reservados.
