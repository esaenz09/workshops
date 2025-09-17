---
title: "Activity 5 - Testing the Model"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists"
difficulty: Intermediate
weight: 8
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/3FELV6BYtIo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

### Probando Nuestro Modelo

Ahora que hemos construido y entrenado nuestro modelo, queremos probarlo con los ítems de ropa que devolvimos. Empecemos con nuestro primer elemento de muestra, que era el zapato.

```python
# Inicia un objeto de modelo con una capa softmax
probability_model = tf.keras.Sequential([model, tf.keras.layers.Softmax()])
```

{{% notice note %}}
Una **capa softmax** es un tipo de capa de red neuronal en un modelo de aprendizaje automático. La capa softmax transforma nuestras entradas, que teóricamente podrían provenir de una variedad de estructuras de datos, en una distribución de probabilidad entre 0 y 1.
{{% /notice %}}

```python
predictions = probability_model.predict(test_images)
```

El código siguiente devuelve una lista de probabilidades de que una imagen pertenezca a una categoría específica. El valor del índice corresponde a qué clase se asignaría a la imagen.
```python
predictions[0] #Returns the index with highest probability, depends on the index value.
```

### Pregunta 1
El arreglo de valores representa el nivel de confianza de que una imagen pertenece a una categoría específica. ¿Qué índice tiene el valor de confianza más alto y cuál tiene el valor de confianza más bajo?

### Pregunta 2
Verifica tu respuesta sobre el valor de máxima probabilidad ejecutando el código a continuación:

```python
np.argmax(predictions[0])
```

```python
test_labels[0]
```

En el arreglo `class_names`, ¿a qué categoría corresponde este índice? (Pista: dado el índice del valor de máxima probabilidad, ¿qué índice deberías buscar?)

Verifica a qué categoría pertenece esta imagen usando este código. ¿Es correcto?

```python
class_names[9]
```