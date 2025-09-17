---
title: "Building the Neural Network"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists, Tuples, Sets"
difficulty: Intermediate
weight: 6
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/ttOhB-w8dt0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Este es el primer paso para construir una **red neuronal**, que en realidad es una herramienta que nos permite hacer **"aprendizaje automático"** (machine learning). Con esta herramienta, entrenamos un programa para analizar imágenes o datos, lo que se conoce como **datos de entrenamiento**. 
Luego del entrenamiento, podemos pedirle al programa que realice y ejecute una tarea específica usando lo que aprendió. Por ejemplo, supongamos que entrenamos un programa con imágenes de perros y gatos, y le proporcionamos al programa la identificación correcta de las imágenes. Una vez entrenado, podemos pedirle al ordenador que identifique si una foto de mi mascota Bigotes (Whiskers) es de un gato o de un perro. 

En nuestro escenario, estamos usando imágenes preetiquetadas de ropa para entrenar nuestro modelo. Luego, queremos que el programa prediga correctamente el tipo de prenda que corresponda a una entrada.

## Reconocer patrones y agrupar elementos

Fíjate en estas dos imágenes.

![Black and white sneaker with white sole](../media/NN_sneaker_ex1.png "Black and white sneaker with white sole")
![Black sneaker](../media/NN_sneaker_ex2.png "Black sneaker")

Como podemos ver en estas imágenes, tenemos dos zapatillas deportivas. Son ambas imágenes distintas y sus valores de píxel varían significativamente, pero aun así podemos categorizarlas como zapatillas. ¿Cómo lo hacemos? Nuestro cerebro interpreta estas imágenes buscando patrones que hemos observado antes y establece: "¡Eso es una zapatilla!"

¿Y por qué se llama zapatilla deportiva? En algún momento todos hemos aceptado colectivamente que esto es diferente de otros tipos de calzado porque las zapatillas tienen cordones, punteras alargadas, suelas gruesas de goma y cubren el pie hasta el tobillo. Probablemente esto es lo que nos dijeron cuando éramos niños: identificar ese tipo de calzado como zapatillas.

¿Qué relevancia tiene esto para lo que haremos a continuación? Tendremos que decirle al ordenador que este tipo de imágenes son zapatillas. No podemos limitarse a marcar estas dos imágenes como zapatillas porque eso sería inefectivo al predecir entradas futuras con este modelo.

Además, no tenemos que quedarnos sólo con zapatillas para categorizar imágenes: podemos usar múltiples categorías para clasificar imágenes (recuerda crear la lista de diferentes categorías de ropa en la Actividad 1). Al final, estas son las categorías que usaremos para ordenar toda la ropa.

## ¿Qué es una red neuronal?

El concepto de **red neuronal** se originó a partir de la idea de replicar el cerebro humano, más específicamente su capacidad para reconocer patrones. De hecho, la palabra “neuronal” deriva de “neurona”, receptores en el cerebro que se activan cuando, por ejemplo, ven una imagen u objeto que reconocen.

En este caso, estamos entrenando al ordenador para reconocer qué es cada imagen (si es un zapato, una camisa, una bolsa, etc.), por lo que nuestro objetivo principal al utilizar la red neuronal en este taller es darle al ordenador la habilidad de clasificar las imágenes del conjunto de datos en diferentes categorías.

La imagen siguiente muestra una implementación sencilla de una red neuronal.

- La capa de entrada es responsable de alimentar datos en el sistema, apuntando a diferentes neuronas para entrenar el modelo.
- La capa oculta consiste en muchas neuronas, que son responsables de reconocer los diferentes patrones a partir de los datos de entrada. Estos nodos luego apuntan a la capa de salida.
- La capa de salida consiste en un nodo único o en varios nodos que devuelven un valor de salida que el modelo predice.

![Neural Network Diagram](../media/neural_network.png "Neural Network Diagram")

En pocas palabras, una red neuronal es un sistema, o un algoritmo, que entrena al ordenador para reconocer diferentes tipos de patrones. 

## ¿Cómo se relaciona con lo que estamos haciendo?

{{% notice note %}}
Recomendamos mirar el primer bloque de código abajo y el diagrama de la red neuronal para entender mejor la relación entre ellos y los puntos siguientes.
{{% /notice %}}

- La capa de entrada toma los distintos tipos de imágenes del conjunto de datos y las alimenta en las neuronas (la capa oculta).
- Las neuronas (128 de ellas) luego reconocen diferentes patrones en las imágenes observando distintas características y las relaciones entre ellas y las categorías predeterminadas. Esta capa le da al ordenador la capacidad de categorizar imágenes por sí mismo.
- La capa de salida consiste en 10 nodos diferentes, que representan las 10 categorías por las que ordenaremos las imágenes. Dependiendo de la imagen específica y de la forma en que el ordenador fue entrenado por las neuronas, la salida será la categoría con mayor probabilidad predicha para esa imagen particular.

{{% notice note %}}

Si te interesa leer más sobre redes neuronales, puedes consultar <a href="https://news.mit.edu/2017/explained-neural-networks-deep-learning-0414" target="_blank">este artículo</a> de MIT News.
 
<a href="https://en.wikipedia.org/wiki/Neural_network#/media/File:Neural_network_example.svg" target="_blank">Fuente de la imagen</a>

{{% /notice %}}

Copia el siguiente código en tu cuaderno de Google Colab:

```python
model = keras.Sequential([ 
    # La primera capa (capa de entrada) transforma cada imagen (la resolución es 28 x 28 píxeles)
    # en un arreglo unidimensional cuyos índices corresponden a todos los píxeles de la imagen.
    keras.layers.Flatten(input_shape=(28, 28)), 
    keras.layers.Dense(128, activation='relu'), # capa oculta
    keras.layers.Dense(10) # capa de salida
])
```


```python
model.compile(optimizer='adam',
              loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])
```

{{% notice note %}}
No te preocupes si no ves ninguna salida después de ejecutar este código. Esto es normal.
{{% /notice %}}