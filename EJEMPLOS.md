# Ejemplos del Método Montecarlo #

## Cálculo de π ##

Uno de los métodos más enseñados para ejemplificar el Método de Montecarlo, es el del cálculo del número pi.

Este método está cerca del experimento de aguja de Buffon, planteada por el naturalista francés Georges-Louis Leclerc de Buffon.

Consideremos al círculo unitario inscrito en el cuadrado de lado 2 centrado en el origen. Dado que el cociente de sus áreas es 
π{\displaystyle \pi }4, el valor de π{\displaystyle \pi } puede aproximarse usando Montecarlo de acuerdo al siguiente método:

1. Dibuja un círculo unitario, y al cuadrado de lado 2 que lo inscribe.
2. Lanza un número n{\displaystyle n} de puntos aleatorios uniformes dentro del cuadrado.
3. Cuenta el número de puntos dentro del círculo, i.e. puntos cuya distancia al origen es menor que 1.
4. El cociente de los puntos dentro del círculo dividido entre n{\displaystyle n} es un estimado de, π{\displaystyle \pi }4. Multiplica el resultado por 4 para estimar π{\displaystyle \pi }.

<img width="330" height="330" alt="Estimacion_de_Pi_por_Montercarlo" src="https://github.com/user-attachments/assets/4d3be2fb-dc73-4809-b9a2-30aff5eabf6c" />

En este cálculo se tienen que hacer dos consideraciones importantes:

1. Si los puntos no están uniformemente distribuidos, el método es inválido.
2. La aproximación será pobre si solo se lanzan unos pocos puntos. En promedio, la aproximación mejora conforme se aumenta el número de puntos.

Ejemplo realizado en java:
