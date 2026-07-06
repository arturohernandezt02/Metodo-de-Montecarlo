# Método de Montecarlo: ¿Qué es y para qué sirve? #
Imagina que quieres saber cuántas veces ganarías una partida si pudieras repetirla un millón de veces. En lugar de jugar realmente un millón de partidas, el método de Montecarlo las simula utilizando números aleatorios y después analiza los resultados obtenidos.
---

El método de Montecarlo es una técnica de simulación probabilística que permite aproximar soluciones a problemas matemáticos complejos cuando obtener un resultado exacto sería demasiado difícil o requeriría una gran cantidad de tiempo y recursos de cómputo.

Su funcionamiento se basa en generar una gran cantidad de valores aleatorios para simular distintos escenarios posibles. A partir de estos escenarios, es posible estimar probabilidades, predecir comportamientos y analizar el impacto de la incertidumbre sobre un problema.

Como curiosidad, su nombre proviene del famoso casino de Montecarlo, en Mónaco. La referencia hace alusión a los juegos de azar, como la ruleta o los dados, donde el resultado depende del azar. De forma similar, este método utiliza números aleatorios para realizar miles o incluso millones de simulaciones y así aproximar la probabilidad de que ocurra un determinado evento.

## Historia del método de Montecarlo

El método de Montecarlo fue desarrollado durante la década de 1940 por John von Neumann y Stanisław Ulam mientras trabajaban en el Laboratorio Nacional de Los Álamos, en Estados Unidos.

Su desarrollo estuvo estrechamente relacionado con el Proyecto Manhattan, donde los investigadores necesitaban estudiar fenómenos extremadamente complejos, como el comportamiento de los neutrones dentro de materiales de fisión. Debido a que estos procesos tienen un comportamiento probabilístico, las simulaciones aleatorias resultaron ser una herramienta muy eficaz para analizarlos.

Aunque los fundamentos del método surgieron alrededor de 1944, su uso se expandió rápidamente gracias al desarrollo de las computadoras, que permitieron ejecutar millones de simulaciones en tiempos cada vez menores.

Actualmente, el método de Montecarlo se utiliza en una gran variedad de áreas, entre ellas:

* Inteligencia artificial.
* Finanzas y análisis de riesgo.
* Pronósticos de ventas y demanda.
* Gestión de proyectos.
* Física e ingeniería.
* Estadística computacional.
* Computación gráfica, especialmente en algoritmos de *ray tracing* para generar imágenes tridimensionales con iluminación realista.

<img width="500" height="707" alt="image" src="https://github.com/user-attachments/assets/094830ae-8b31-4f06-a1dd-8c6d981c2a9a" />

## ¿Cómo funciona la simulación de Montecarlo?

A diferencia de un modelo tradicional, que utiliza un único valor para cada variable de entrada, una simulación de Montecarlo considera que algunas variables pueden tomar diferentes valores dentro de un rango de posibilidades.

Para representar esa incertidumbre, a cada variable se le asigna una distribución de probabilidad, como una distribución uniforme o una distribución normal. Posteriormente, el algoritmo genera valores aleatorios siguiendo dicha distribución y calcula el resultado del modelo.

Este proceso se repite miles o incluso millones de veces. En cada iteración cambian los valores de entrada, lo que produce un nuevo resultado. Al finalizar todas las simulaciones, se obtiene una distribución de resultados posibles en lugar de un único valor.

Gracias a este enfoque, el método no solo permite estimar cuál es el resultado más probable, sino también conocer la probabilidad de que ocurran distintos escenarios y evaluar el nivel de incertidumbre asociado al problema.

