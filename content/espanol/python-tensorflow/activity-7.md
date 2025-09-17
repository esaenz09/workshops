---
title: "Activity 7 - Plotting an Image's predicted Category"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists"
difficulty: Intermediate
weight: 12
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/pwZDPj4yIsM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Trazando la categoría de una imagen
</br>
Puede recordar que, cuando trazamos los modelos, el eje x de los gráficos estaba etiquetado con los números del 0 al 9. Estos corresponden a las categorías de artículos que definimos anteriormente en el taller, es decir: t-shirt/top, trouser, pullover, dress, coat, sandal, shirt, sneaker, bag y ankle boot.
</br>

![Plotting Model Figure 2 of a sneaker](../media/Plotting_fig2.png "Pixelated sneaker with color bar")

</br>
Ajustaremos el etiquetado del eje x para que los datos que muestra sean más fáciles de entender.
</br>
</br>
Copia y pega el siguiente código en tu cuaderno de Google Colab:

```python
img = test_images[0] # Toma una imagen del conjunto de prueba.
# NOTA: Este índice se cambiará y su gráfico correspondiente se mostrará en los siguientes pasos

print(img.shape) # Esto muestra la resolución de la imagen.
```


```python
img = (np.expand_dims(img,0)) # Esto expande el arreglo img

print(img.shape)
```


```python
# Esto da el nivel de confianza de que la imagen corresponde a cada categoría.
# Por ejemplo, la probabilidad de que la imagen sea una camiseta (T-shirt) es 5.2198538e-07.
predictions_single = probability_model.predict(img)

print(predictions_single)
```


```python
plot_value_array(0, predictions_single[0], test_labels)  

# Grafica y etiqueta el eje x con los class_names
# también conocidos como las categorías que hicimos en la Actividad 1
_ = plt.xticks(range(10), class_names, rotation=45)
```

Para verificar el valor de índice con la mayor probabilidad, usamos el siguiente código.

```python
# La salida de esto nos dice a qué categoría tenía la mayor probabilidad 
# de pertenecer la prenda
np.argmax(predictions_single[0]) 
```

## Experimentando con los gráficos

En el primer segmento de código de esta actividad, cambia el valor del índice para el arreglo `test_images` a cualquier número de tu elección.

### Pregunta 1
En `plot_value_array`, cambia el primer parámetro al mismo número de índice usado anteriormente. ¿Qué nombre de clase tiene la mayor probabilidad?

Verifica tu respuesta ejecutando el código abajo para mostrar la imagen especificada y el gráfico de la categoría que el modelo predijo.

¿Es esto consistente con la respuesta de tu pregunta anterior?

```python
i = your_desired_value   # Podemos ver que esta imagen detecta el nombre de clase correcto para la imagen
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```