# GUÍA DE INTEGRACIÓN Y CONFIGURACIÓN EN MOODLE
## Suite de Juegos Serios 3D - Salud Mental y Prevención del Riesgo Psicosocial
### Seguros Bolívar ARL • Campus Virtual y Plataformas de Empresas Afiliadas

---

## 1. Introducción y Requisitos Previos

Esta guía instruye paso a paso a los **Administradores de Plataforma y Diseñadores Tecno-pedagógicos de Seguros Bolívar** en la correcta carga, parametrización y validación de los paquetes SCORM dentro de aulas virtuales soportadas en **Moodle** (versiones 3.9 a 4.4+).

### 1.1 Archivos Disponibles
Los paquetes listos para producción se encuentran en la carpeta `scorm/`:
* `Juego_01_RadioObra_SCORM.zip` (Unidad 1 - Canal Limpio)
* `Juego_02_ArquitectoTiempo_SCORM.zip` (Unidad 2 - El Arquitecto del Tiempo)
* `Juego_03_SantuarioRecarga_SCORM.zip` (Unidad 3 - Santuario de Recarga)
* `Juego_04_SolitarioQuincena_SCORM.zip` (Unidad 4 - La Ruta de tu Quincena 3D)
* `Juego_05_VocesCuadrilla_SCORM.zip` (Unidad 5 - Voces de Cuadrilla)

---

## 2. Procedimiento de Carga Paso a Paso

1. Inicie sesión en el **Campus Virtual de Seguros Bolívar** con credenciales de Administrador o Docente Editor.
2. Ingrese al curso de **Salud Mental y Riesgo Psicosocial en Obra**.
3. Active el modo de edición (botón superior derecho **Activar edición** o interruptor **Modo edición**).
4. Desplácese a la sección correspondiente a la unidad didáctica y pulse en **+ Añadir una actividad o un recurso**.
5. En la pestaña de actividades, seleccione **Paquete SCORM**.
6. Se abrirá el formulario de configuración. Proceda a diligenciar cada sección según los parámetros que se detallan a continuación.

---

## 3. Matriz de Configuración Exacta de Parámetros en Moodle

### 3.1 Sección General
* **Nombre:** Nombre oficial de la experiencia (ejemplo: `Módulo 5: Simulación 3D - Voces de Cuadrilla`).
* **Descripción:** 
  > *Simulación inmersiva en 3D para el reconocimiento emocional somático y la resolución asertiva en frentes de obra. Al ingresar, active sus auriculares o altavoces y siga las instrucciones en pantalla. Se requiere un puntaje mínimo de 80/100 para aprobar.*
* **Muestra la descripción en la página del curso:** Opcional (desmarcado por defecto).

### 3.2 Sección Paquete
* **Archivo del paquete:** Arrastre y suelte el archivo ZIP correspondiente (ej. `Juego_05_VocesCuadrilla_SCORM.zip`).

### 3.3 Sección Apariencia (Crítica para el Motor 3D)
| Parámetro en Moodle | Valor Requerido | Explicación Técnica |
| :--- | :--- | :--- |
| **Mostrar paquete** | **En una ventana nueva** | Evita colisiones de CSS y garantiza que Three.js utilice el 100% de la aceleración gráfica del navegador sin recortes. |
| **Ancho de ventana** | `100%` (o `1280`) | Proporciona visualización horizontal completa de maquetas y cuadrillas. |
| **Alto de ventana** | `100%` (o `850`) | Asegura que la consola de decisiones inferior y los subtítulos no queden ocultos. |
| **Opciones de ventana** | Marcar **Permitir que la ventana sea redimensionada** | Permite al usuario maximizar la pantalla en monitores externos. |
| **Mostrar nombre de la actividad** | Desmarcado / No | El encabezado interno del juego ya contiene el membrete institucional. |
| **Ocultar estructura del curso** | Sí | Elimina paneles laterales que distraen de la simulación. |
| **Ocultar botones de navegación** | Sí | La navegación se efectúa mediante los botones de avance del propio juego. |

### 3.4 Sección Calificación
* **Método de calificación:** `Calificación más alta`.
* **Calificación máxima:** `100`.
* **Calificación para aprobar (Grading to pass):** `80`.

### 3.5 Sección Intentos
* **Número de intentos:** `3 intentos` (Recomendado para aprendizaje reflexivo formativo; permite corregir decisiones erróneas).
* **Calificación de intentos:** `Calificación más alta`.
* **Forzar nuevo intento:** `No`.
* **Bloquear después del intento final:** `Sí`.

### 3.6 Sección Finalización de Actividad
* **Rastreo de finalización:** `Mostrar la actividad como completada cuando se cumplan las condiciones`.
* **Requerir ver:** `El estudiante debe ver esta actividad para completarla` (Marcado).
* **Requerir calificación:** `El estudiante debe recibir una calificación para completar esta actividad` (Marcado).
* **Requerir estado SCORM:** Marcar las casillas `Pasado (Passed)` y `Completado (Completed)`.

---

## 4. Verificación y Pruebas de Despliegue

Antes de liberar el aula virtual a los trabajadores afiliados, realice la siguiente lista de verificación:

- [ ] **Acceso en Modo Estudiante:** Cambie su rol a "Estudiante" en Moodle e ingrese a la actividad.
- [ ] **Apertura de Ventana:** Verifique que el juego abra en ventana emergente sin barras de scroll duplicadas.
- [ ] **Render 3D y Sonido:** Compruebe que la escena 3D cargue con fluidez y que la voz sintetizada se active tras hacer clic en pantalla.
- [ ] **Reporte en Calificador:** Complete la simulación hasta la pantalla de informe y verifique en el Libro de Calificaciones de Moodle que la nota (`cmi.core.score.raw`) y el estado de finalización aparezcan registrados inmediatamente.

