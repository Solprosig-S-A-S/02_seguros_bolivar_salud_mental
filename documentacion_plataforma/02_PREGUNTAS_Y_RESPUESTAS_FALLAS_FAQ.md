# PREGUNTAS Y RESPUESTAS FRECUENTES (FAQ) Y TROUBLESHOOTING
## Suite de Juegos Serios 3D - Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Soporte Técnico de Plataforma LMS

---

### P1: ¿Por qué no escucho la voz ni los efectos sonoros al entrar al juego?
* **Causa:** Las políticas modernas de los navegadores (Google Chrome, Microsoft Edge, Safari) bloquean la reproducción automática de audio (*autoplay*) hasta que el usuario realiza su primera interacción consciente en la página.
* **Solución:**
  1. Haga un clic o toque en cualquier área del juego al ingresar para habilitar el subsistema de audio.
  2. Verifique que la pestaña del navegador no tenga el icono de altavoz silenciado (`Silenciar pestaña`).
  3. Asegúrese de que el volumen de su equipo o auriculares esté activo.
  4. Recuerde que **todos los diálogos y respuestas cuentan con subtítulos sincronizados en pantalla**, garantizando que el usuario pueda completar la formación sin barreras si su equipo no dispone de altavoces.

---

### P2: La pantalla 3D se ve negra, lenta o con retraso al girar la cámara.
* **Causa:** La aceleración gráfica por hardware del navegador está desactivada o los controladores de video requieren actualización.
* **Solución:**
  1. En **Google Chrome** o **Microsoft Edge**:
     * Ingrese en la barra de direcciones: `chrome://settings/system` (o `edge://settings/system`).
     * Active la casilla: **"Usar aceleración por hardware cuando esté disponible"**.
     * Reinicie el navegador.
  2. Si está en un equipo corporativo de oficina remota, evite abrir la simulación a través de conexiones de Escritorio Remoto (RDP) de bajo ancho de banda que no retransmiten WebGL.

---

### P3: En Moodle o Canvas el juego se muestra recortado o con doble barra de desplazamiento vertical.
* **Causa:** El recurso SCORM fue configurado para incrustarse en la misma ventana dentro de un marco (*iframe*) de altura fija insuficiente.
* **Solución para el Administrador LMS:**
  1. Edite los ajustes de la actividad SCORM en el aula virtual.
  2. En la sección **Apariencia**, cambie el parámetro **Mostrar paquete** a: **En una ventana nueva**.
  3. Defina el ancho y alto en `100%` (o mínimo `1280 x 850 px`) y active la opción **Permitir redimensionar ventana**.

---

### P4: El trabajador completó todas las estaciones pero la nota no aparece en el calificador del LMS.
* **Causa:** El usuario cerró la pestaña del navegador de forma abrupta antes de presionar el botón final de guardado o informe.
* **Solución:**
  1. El paquete SCORM transmite la instrucción `cmi.core.lesson_status = "passed"` y ejecuta `LMSCommit()` cuando el usuario pulsa el botón **Ver Informe y Guardar** / **Finalizar Evaluación**.
  2. Es indispensable orientar a los trabajadores para que completen la experiencia hasta la pantalla final y no cierren la ventana antes de ver su resumen de aprobación.

---

### P5: ¿Qué sucede si el juego se abre en un entorno sin conexión LMS (GitHub Pages o intranet local)?
* **Respuesta:** Los 5 juegos cuentan con un **mecanismo de fallback seguro**. Si el código no detecta el conector SCORM (`window.API`), la simulación se ejecuta con total normalidad en modo autónomo, permitiendo explorar los contenidos, responder las preguntas y visualizar el reporte final en pantalla sin arrojar errores técnicos.

---

### P6: ¿Se recopilan datos confidenciales o nombres de los trabajadores en servidores externos?
* **Respuesta:** **No.** La suite no realiza ninguna llamada a servidores de terceros ni almacena datos privados fuera del entorno seguro de su LMS. Todo el cómputo se realiza localmente en la memoria del navegador del usuario y los resultados se envían exclusivamente a la base de datos de su propia plataforma Moodle / LMS corporativo.

