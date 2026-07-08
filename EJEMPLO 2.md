# Ejemplo 2: Estimación de la duración de un proyecto

Otra de las aplicaciones más comunes del método de Montecarlo consiste en **estimar la duración total de un proyecto** cuando el tiempo necesario para completar cada tarea es incierto.

Supongamos que un proyecto está compuesto por tres actividades:

| Actividad  |  Tiempo estimado |
| ---------- | ---------------: |
| Análisis   | Entre 2 y 4 días |
| Desarrollo | Entre 5 y 9 días |
| Pruebas    | Entre 1 y 3 días |

En un enfoque tradicional podría asumirse que cada actividad tarda exactamente un valor promedio. Sin embargo, en la práctica siempre existe incertidumbre: algunas tareas terminan antes de lo previsto y otras requieren más tiempo.

La simulación de Montecarlo modela esta incertidumbre asignando una **distribución de probabilidad** al tiempo de cada actividad. En cada simulación se genera un tiempo aleatorio para cada tarea y posteriormente se calcula la duración total del proyecto.

Por ejemplo, una simulación podría generar los siguientes valores:

| Actividad  | Tiempo generado |
| ---------- | --------------: |
| Análisis   |          3 días |
| Desarrollo |          8 días |
| Pruebas    |          2 días |
| **Total**  |     **13 días** |

En la siguiente simulación los valores serían diferentes:

| Actividad  | Tiempo generado |
| ---------- | --------------: |
| Análisis   |          2 días |
| Desarrollo |          6 días |
| Pruebas    |          3 días |
| **Total**  |     **11 días** |

Este procedimiento se repite miles de veces. Al finalizar, en lugar de obtener una única duración posible, se obtiene una distribución de resultados que permite responder preguntas como:

* ¿Cuál es la duración más probable del proyecto?
* ¿Cuál es la probabilidad de terminar antes de una fecha determinada?
* ¿Qué tan frecuente es que el proyecto se retrase?

Gracias a esta información, los responsables del proyecto pueden planificar con mayor confianza, identificar riesgos y establecer cronogramas más realistas. Este tipo de simulaciones es ampliamente utilizado en la gestión de proyectos, la ingeniería y la planificación de operaciones.
