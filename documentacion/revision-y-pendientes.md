# Revisión y pendientes

Fecha de referencia: 22 de octubre de 2026.

## Ajustes realizados

1. Portal: se añadió la apertura directa del tercer juego con `?game=3`.
2. Juego 2: el `masteryscore` del manifiesto se alineó a 75, coincidiendo con la lógica y los textos del juego.
3. Juego 3: el adaptador SCORM busca en la ventana actual y sus ancestros, y luego en la ventana que abrió el juego y sus ancestros. Se evita recorrer repetidamente una ventana que es su propio padre y se toleran ancestros inaccesibles.
4. Juego 3: solo se considera inicializado si `LMSInitialize` devuelve `true` o `'true'`; una inicialización rechazada no produce escrituras. Se evita inicializar dos veces una sesión activa.
5. Se sincronizaron los paquetes SCORM de los juegos 2 y 3 con sus fuentes.

## Mejoras identificadas

Estas observaciones no constituyen funcionalidades implementadas ni validaciones normativas o clínicas.

- **Informes generales:** los resultados se construyen por aprobado/reprobado, sin conservar un historial individual de respuestas. Pueden atribuir al participante acciones que no eligió. El juego 2 permite aprobar con un error y aun así anuncia cero accidentes.
- **Juego 3 y evaluación:** el final fallido existe, pero el flujo normal no ofrece omisiones ni decisiones incorrectas. Conviene definir si se conserva como práctica guiada o se diseña una evaluación con alternativas.
- **Reanudación:** no hay restauración del avance tras cerrar, recargar o abandonar la sesión.
- **Cierre LMS:** no hay gestión explícita de salida por cierre de pestaña; el flujo depende del botón de finalización. Las pantallas de cierre pueden anunciar registro aunque la ejecución sea autónoma.
- **Accesibilidad:** hay controles basados en `div` y eventos de clic o puntero sin equivalentes completos de teclado. No se identificó una preferencia de movimiento reducido.
- **Dependencias externas:** Three.js y las fuentes requieren red; el empaquetado no garantiza funcionamiento completamente desconectado.
- **Contenido especializado:** los textos contienen referencias legales, estadísticas y afirmaciones fisiológicas que requieren revisión con fuentes autorizadas. Valores como 68 BPM se muestran como resultados de la simulación, sin medición biométrica.

## Alcance de la comprobación

Se revisaron código, estructura, flujos, puntuaciones, adaptadores y manifiestos. Se comprobó la sintaxis de los scripts, las rutas del portal, el comportamiento del adaptador modificado con APIs simuladas y la correspondencia entre fuentes y ZIP.

Quedan pendientes pruebas visuales y partidas completas en navegador, dispositivos táctiles y un LMS real. La revisión de código no acredita el rendimiento gráfico, la accesibilidad completa ni la validez de los contenidos normativos y clínicos.
