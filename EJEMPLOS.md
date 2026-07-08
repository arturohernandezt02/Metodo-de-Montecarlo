# Ejemplos del método de Montecarlo

## Ejemplo 1: Estimación del número $\pi$

Uno de los ejemplos más conocidos para comprender el funcionamiento del método de Montecarlo consiste en **estimar el valor del número $\pi$** utilizando puntos generados aleatoriamente.

La idea está relacionada con el **experimento de la aguja de Buffon**, propuesto por el matemático francés **Georges-Louis Leclerc de Buffon**, quien demostró que era posible aproximar el valor de $\pi$ mediante experimentos probabilísticos.

### Fundamento matemático

Consideremos un **círculo unitario** (radio igual a 1) inscrito dentro de un cuadrado de lado 2, ambos centrados en el origen.

<p align="center">
<img width="330" height="330" alt="Estimación de Pi mediante Montecarlo" src="https://github.com/user-attachments/assets/4d3be2fb-dc73-4809-b9a2-30aff5eabf6c" />
</p>

El área del círculo es

$$
A_{círculo}=\pi r^2=\pi
$$

ya que $r=1$.

Por otro lado, el área del cuadrado es

$$
A_{cuadrado}=2^2=4.
$$

Por lo tanto, la relación entre ambas áreas es

$$
\frac{A_{\text{círculo}}}{A_{\text{cuadrado}}} =
\frac{\pi}{4}
$$

Si los puntos se distribuyen **uniformemente** dentro del cuadrado, la proporción de puntos que caen dentro del círculo será aproximadamente igual a esa relación de áreas. Es decir,

$$
\frac{\text{Puntos dentro del círculo}}
{\text{Total de puntos}}
\approx
\frac{\pi}{4}.
$$

Despejando $\pi$, obtenemos la expresión utilizada en la simulación:

$$
\pi \approx
4
\cdot
\frac{\text{Puntos dentro del círculo}}
{\text{Total de puntos}}.
$$

### Algoritmo

El procedimiento puede resumirse en los siguientes pasos:

1. Dibujar un círculo unitario inscrito en un cuadrado de lado 2.
2. Generar **$N$ puntos aleatorios** distribuidos uniformemente dentro del cuadrado.
3. Verificar cuáles de esos puntos caen dentro del círculo, es decir, aquellos que cumplen:

$$
x^2+y^2\le1.
$$

4. Contar la cantidad de puntos que quedaron dentro del círculo.
5. Aplicar la expresión anterior para obtener una aproximación de $\pi$.

### Consideraciones

Para que el método produzca una buena aproximación deben cumplirse dos condiciones importantes:

* Los puntos deben generarse con una **distribución uniforme**; de lo contrario, la estimación será incorrecta.
* Mientras mayor sea el número de puntos generados, mejor será la aproximación obtenida. Esto se debe a que el error disminuye conforme aumenta el número de simulaciones.

### Implementación en Java

El siguiente programa implementa este procedimiento utilizando números aleatorios para estimar el valor de $\pi$.

```
import java.util.Random;

public class MyClass {

    public static void main(String[] args) {

        int n = 10_000_000;
        int insideCircle = 0;

        Random rand = new Random();

        for (int i = 0; i < n; i++) {

            double x = rand.nextDouble(2) - 1.0;
            double y = rand.nextDouble(2) - 1.0;

            if (isInsideCircle(x, y)) {
                insideCircle++;
            }
        }

        double pi = 4.0 * insideCircle / n;

        System.out.println("Valor aproximado de π: " + pi);
    }

    public static boolean isInsideCircle(double x, double y) {
        return x * x + y * y <= 1.0;
    }

}
```

## Ejemplo 2: Estimación de la duración de un proyecto

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
