---
title: "Activity 1 - Importing the TensorFlow library and datasets"
date: 2020-09-09T16:19:17-07:00
prereq: "Conceptos básicos de Python: Funciones - Funciones incorporadas, Funciones de bibliotecas; Tipos de datos - Cadenas, Números, Lectura desde la consola; Estructuras de datos - Listas"
difficulty: Intermediate
weight: 2
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/OxDn2xDXWi4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Importar dependencias

#### Paquetes
Lo primero que debemos hacer es importar la biblioteca TensorFlow para poder usar funciones que nos permitirán entrenar nuestro modelo.

También implementaremos gráficas para visualizar las predicciones de nuestro modelo, por lo que para eso necesitamos importar las siguientes bibliotecas:

```python
# Importar TensorFlow y las librerías tf.keras

import tensorflow as tf
from tensorflow import keras 

# Librerías auxiliares para estadísticas y para crear gráficos

import numpy as np
import matplotlib.pyplot as plt 
```

Estas bibliotecas son esenciales ya que son una colección de métodos y funciones precompilados; al importarlas en nuestro programa podemos acceder a esos métodos sin tener que reescribir toda la biblioteca. Por ejemplo, importamos los métodos y funciones de TensorFlow y NumPy para evitar tener que escribir la totalidad de esos programas dentro del nuestro.

#### Cargar conjuntos de datos
Ahora queremos cargar el conjunto de datos Fashion MNIST, que contiene la colección de todas las imágenes de ropa que necesitamos para nuestro modelo.

```python
# Esta variable se declara desde la librería fashion_mnist en la sección datasets

fashion_mnist = keras.datasets.fashion_mnist 
```

```python
# Esto carga cuatro variables desde el conjunto de datos.
# train_images y train_labels son los datos que el modelo usa para aprender.
# test_images y test_labels son usados por el modelo para comparar y evaluar.

(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data() 
```

{{% notice note %}}
Podrás notar que estamos dividiendo los datos en conjuntos de entrenamiento y prueba con sus correspondientes etiquetas. Un **conjunto de entrenamiento** es para que nuestro modelo aprenda los parámetros óptimos para realizar la tarea, mientras que el **conjunto de prueba** sirve para validar qué tan bien ha aprendido el modelo. ¡Es parecido a cómo aprendemos nosotros: somos continuamente entrenados y evaluados para mejorar!
{{% /notice %}}

<br>

### Preparar nuestros datos

El siguiente paso es crear una lista de categorías bajo la variable `class_names`.

Tu supervisor te da las categorías de prendas que procesa el almacén. Esto se creará en la variable `class_names`.

{{% notice tip %}}

<a href="https://workshops.nuevofoundation.org/python-basics/data-structures/lists/" target="_blank">¿No sabes cómo crear una lista en Python?</a>

### Tarea 1

Escribe los siguientes nombres de clase en la lista `class_names`:

- Camiseta/top
- Pantalón
- Suéter
- Vestido
- Abrigo
- Sandalia
- Camisa
- Zapatilla deportiva
- Bolso
- Botín

{{% /notice %}}

{{% notice info %}}
### Lectura opcional

Si te interesa aprender más sobre estas bibliotecas en detalle, siéntete libre de visitar los siguientes sitios web.

<a href="https://www.tensorflow.org/overview" target="_blank">Aprende sobre TensorFlow</a>

<a href="https://www.w3schools.com/python/numpy_intro.asp" target="_blank">Aprende sobre NumPy</a>

<a href="https://matplotlib.org/" target="_blank">Aprende sobre Matplotlib</a>

{{% /notice %}}