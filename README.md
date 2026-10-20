# Experiencias Gamificadas de Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Resolución 2764 de 2022 y Ley 1010 de 2006

Repositorio de simulaciones interactivas en 3D desarrolladas con **Three.js**, listas para su despliegue inmediato en **GitHub Pages** y empaquetadas como Objetos Virtuales de Aprendizaje compatibles con **SCORM 1.2** para plataformas LMS empresariales.

---

## 🌐 Acceso Directo en GitHub Pages

Al habilitar **GitHub Pages** en la rama `main` (directorio `/root`), el proyecto queda publicado y navegable de inmediato:

* **Portal Principal (Hub de Juegos):** [`index.html`](file:///./index.html)
* **Juego 01 (Canal Limpio en Primera Persona):** [`juego1.html`](file:///./juego1.html) *(o `juego-01.html`)*
* **Juego 02 (El Arquitecto del Tiempo Isométrico):** [`juego2.html`](file:///./juego2.html) *(o `juego-02.html`)*

---

## 🎮 Contenido del Repositorio

### 1. [Juego 01: Radio Obra - Canal Limpio](file:///./juego1.html)
* **Ubicación:** `juego1.html` (en raíz) y carpeta LMS [`Juego_01_RadioObra_CanalLimpio/`](file:///./Juego_01_RadioObra_CanalLimpio/)
* **Formato:** Aventura en Primera Persona 3D con navegación peatonal cinemática y rotación libre táctil 360°.
* **Enfoque Psicosocial:** Comunicación asertiva, claridad de rol, prevención del acoso laboral (Ley 1010 de 2006), primeros auxilios psicológicos (PAP) y desescalamiento de crisis colectiva.
* **Mecánica:** Desplazamiento por 10 estaciones de trabajo realistas en losa de piso 5, interacción con cuadrilla mediante bocadillos proyectados en 3D, y toma de decisiones éticas con consecuencias visibles en el entorno.
* **Entregables:** Código autónomo en raíz (`juego1.html`), paquete listo para LMS `Juego_01_RadioObra_SCORM.zip` y manifiesto `imsmanifest.xml`.

### 2. [Juego 02: El Arquitecto del Tiempo - Carga Mental](file:///./juego2.html)
* **Ubicación:** `juego2.html` (en raíz) y carpeta LMS [`Juego_02_ArquitectoTiempo_CargaMental/`](file:///./Juego_02_ArquitectoTiempo_CargaMental/)
* **Formato:** Simulación Isométrica 3D estilo *Bento Box* con rotación orbital e iluminación direccional.
* **Enfoque Psicosocial:** Gestión de la carga mental y sobrecarga cognitiva, ambigüedad/conflicto de órdenes, liderazgo preventivo y relaciones interpersonales en obra.
* **Mecánica:** 
  * 4 frentes críticos con animación concreta en tiempo real (trompo mezclador, grúa torre con carga oscilante por viento, borde perimetral a 18 m y pasillo central de relevo).
  * **Consola de Decisión Directa:** Opciones compactas con evaluación inmediata, manteniendo despejado más del 75% del visor 3D para apreciar la simulación.
  * Semáforo dinámico de Carga Mental (Enfocado, Alerta, Sobrecarga).
* **Entregables:** Código autónomo en raíz (`juego2.html`), paquete listo para LMS `Juego_02_ArquitectoTiempo_SCORM.zip` y manifiesto `imsmanifest.xml`.

---

## 🛠️ Especificaciones Técnicas

* **Despliegue GitHub Pages:** Archivo `index.html` en la raíz como portal unificado con ejecutor embebido y acceso directo a cada juego.
* **Motor Gráfico:** Three.js (r128) nativo sin dependencias de compilación externa.
* **Estilo Visual:** Paleta corporativa Seguros Bolívar (azul marino `#023047`, amarillo `#FFB703`, verde azulado `#2A9D8F`), tipografía fluida *Plus Jakarta Sans* y superficies translúcidas con *glassmorphism* (`backdrop-filter`).
* **Iconografía:** 100% vector SVG nativo (0 emojis, apto para entornos corporativos e institucionales).
* **Compatibilidad:** Responsive design adaptado a pantallas táctiles móviles, tabletas y computadores de escritorio.
* **Estándar SCORM:** SCORM 1.2 (`LMSInitialize`, `LMSSetValue`, `LMSCommit`, `LMSFinish`) con soporte de ejecución autónoma (fallback seguro cuando no se detecta API LMS).

---

## 📄 Licencia y Derechos

Desarrollado para **Seguros Bolívar ARL**. Todos los derechos reservados.
