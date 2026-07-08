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
import java.awt.geom.Point2D;
   import java.util.Random;
   public class MyClass {
       public static void main(String args[]) {
         int n=10000000;
         int insideCircle = 0;
         for(int i = 1; i <= n; i++){
             Random rand = new Random();
             double x = rand.nextDouble(2) -1d;
             double y = rand.nextDouble(2) -1d;
             if(isInsideCircle(x,y)){
                 insideCircle++; 
             }
         }
         System.out.println("pi value: " + 4*(double)insideCircle/(double)n);
       }
       
       public static boolean isInsideCircle( 
           double x1, 
           double y1) {
           return Point2D.distance(x1, y1, 0, 0) <= 1;
       }
   }
```

