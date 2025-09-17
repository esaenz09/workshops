---
title: "Plotting the Model and its Predictions"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists, Tuples, Sets; Loops- For Loops"
difficulty: Intermediate
weight: 11
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/FrO66fkSU7M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

</br>
</br>

Ahora que podemos clasificar la categoría de una prenda individual usando nuestro modelo, visualizaremos estas predicciones creando un gráfico de barras para una imagen especificada.

## Clasificación predicha

La función plot_image muestra una imagen junto con su clasificación predicha, el nivel de confianza del modelo para esa categoría y la clasificación real (para referencia).

{{% notice tip %}}
Un nivel de confianza se usa para indicar cuán seguro estamos de que nuestra respuesta es correcta. Si tienes que predecir si lloverá mañana, tus respuestas posibles son sí o no. ¿Y si no estás totalmente seguro de tu respuesta? Si el meteorólogo predijo lluvia para mañana, podrías decir que estás 90% confiado. Esto significa que estás bastante seguro de que lloverá mañana, pero también nos dice que piensas que hay un 10% de probabilidad de estar equivocado.

Un nivel de confianza más bajo indica que estás menos seguro de que tu respuesta sea correcta, es decir, que es más probable que estés equivocado en algún grado. Cuanto más cerca esté el nivel de confianza del 100%, más seguro estamos de nuestra predicción.
{{% /notice %}}

Copia la función plot_image en tu cuaderno de Google Colab:
</br>

```python
def plot_image(i, predictions_array, true_label, img):
  true_label, img = true_label[i], img[i]
  plt.grid(False)
  plt.xticks([])
  plt.yticks([])

  plt.imshow(img, cmap=plt.cm.binary)

  predicted_label = np.argmax(predictions_array)
  if predicted_label == true_label:
    color = 'blue'
  else:
    color = 'red'

  plt.xlabel("{} {:2.0f}% ({})".format(class_names[predicted_label],
                                100*np.max(predictions_array),
                                class_names[true_label]),
                                color=color)
```

## Visualización de los valores de confianza

La función plot_value_array dibuja los valores de confianza generados por el modelo como un gráfico de barras.

El eje y del gráfico mostrará el nivel de confianza, mientras que el eje x representará la categorización de los artículos (t-shirt/top, trouser, pullover, dress, coat, sandal, shirt, sneaker, bag, o ankle boot).

Copia la función plot_value_array en tu cuaderno de Google Colab:

```python 
def plot_value_array(i, predictions_array, true_label):
  true_label = true_label[i]
  plt.grid(False)
  plt.xticks(range(10))
  plt.yticks([])
  thisplot = plt.bar(range(10), predictions_array, color="#777777")
  plt.ylim([0, 1])
  predicted_label = np.argmax(predictions_array)

  thisplot[predicted_label].set_color('red')
  thisplot[true_label].set_color('blue')
```

## Uso de las funciones

Usaremos el siguiente código para llamar a las funciones que escribimos anteriormente. Copia el fragmento en tu cuaderno de Google Colab.

```python
i = 0   
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```

![Plotting Model Figure 1 of an ankle boot](../media/Plotting_fig1.png "Plotting Model Figure 1 of an ankle boot")

Podemos ver que nuestro modelo predice que este artículo es un ankle boot (botín). ¿Qué tan confiado está el modelo en esta predicción? 99% confiado. La categoría entre paréntesis es la clasificación correcta del artículo. En este caso, el modelo detectó el artículo correctamente.
</br>
</br>
Ten en cuenta que no todos los modelos son perfectos. Los modelos pueden equivocarse, como veremos en el siguiente ejemplo.
</br>

Usaremos el mismo código de antes, pero probaremos la confianza con un artículo diferente. Asigna a i un nuevo valor, por ejemplo 12.

```python
i = 12 
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```

![Plotting Model Figure 2 of a sneaker](../media/Plotting_fig2.png "Plotting Model Figure 2 of a sneaker")

En este ejemplo vemos que el modelo predijo que el artículo es una sandal (sandalia) con un 96% de confianza. Sin embargo, la identificación correcta del artículo es sneaker (zapatilla deportiva). El gráfico muestra que el modelo también predijo que el artículo era una sneaker con ~3% de confianza o un ankle boot con ~1% de confianza.

## Más ejemplos

Para más ejemplos de las predicciones del modelo, grafica las primeras 25 imágenes de test, sus etiquetas predichas y las etiquetas reales. Como antes, las predicciones correctas se mostrarán en azul y las incorrectas en rojo.

Copia este código en tu cuaderno de Google Colab:

```python
num_rows = 5
num_cols = 5
num_images = num_rows*num_cols
plt.figure(figsize=(2*2*num_cols, 2*num_rows))
for i in range(num_images):
  plt.subplot(num_rows, 2*num_cols, 2*i+1)
  plot_image(i, predictions[i], test_labels, test_images)
  plt.subplot(num_rows, 2*num_cols, 2*i+2)
  plot_value_array(i, predictions[i], test_labels)
plt.tight_layout()
plt.show()
```
![Plotting Model Figure 3, 5x5 images and their model predictions](../media/Plotting_fig3.png "Plotting Model Figure 3, 5x5 images and their model predictions")

¿Qué te parecen las predicciones del modelo? ¿Estarías satisfecho con esta tasa de acierto?