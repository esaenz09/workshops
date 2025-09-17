---
title: "Answer Key"
date: 2020-09-14T16:19:17-07:00
weight: 15
draft: false
hidden: true
---

## Actividad 1
#### Tarea 1:

```python
class_names = ['T-shirt/top', 'Trouser', 'Pullover', 'Dress', 'Coat','Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot']  
```

## Actividad 2
#### Pregunta 1:
```python
plt.figure()
plt.imshow(train_images[7]) # Muestra la primera imagen del conjunto de datos como un gráfico o píxeles de diferentes colores
plt.colorbar() # Muestra la barra de color a la derecha
plt.grid(False)
plt.show() # Muestra todo el gráfico
```
#### Pregunta 2: 
¡255!
El valor máximo de píxel es 255 para cualquier índice utilizado.

## Actividad 3
#### Pregunta 1:
Para responder Q1 deberías cambiar tu código a lo siguiente:
```python
plt.figure(figsize=(10,10)) # establece el tamaño de la imagen a 10x10 píxeles
for i in range(42): # muestra las primeras 42 imágenes con su nombre de clase
    plt.subplot(6,7,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary) 
    plt.xlabel(class_names[train_labels[i]])
plt.show() # muestra las imágenes con sus etiquetas 
```
![images 6x7](../media/PU2_42images.png "images 6x7 with labels")


## Actividad 4
Las respuestas pueden variar; se proporcionan respuestas de ejemplo a continuación:
### Pregunta 1

```python
model.fit(train_images, train_labels, epochs=2) # los epochs determinan cuántas veces se entrena un modelo
```
```
Epoch 1/2
1875/1875 [==============================] - 4s 2ms/step - loss: 0.5024 - accuracy: 0.8231
Epoch 2/2
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3761 - accuracy: 0.8647
<tensorflow.python.keras.callbacks.History at 0x7f909cbb2208>
```

```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)

print('\nTest accuracy:', test_acc)
```
```
313/313 - 0s - loss: 0.3899 - accuracy: 0.8604

Test accuracy: 0.8604000210762024
```

La precisión en el Epoch 2 es 0.8647 y la precisión en el conjunto de prueba cuando se compara el modelo entrenado con el conjunto de test es 0.8604.

#### Pregunta 2
```python
model.fit(train_images, train_labels, epochs=10) # los epochs determinan cuántas veces se entrena un modelo
```
```
Epoch 1/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.4990 - accuracy: 0.8247
Epoch 2/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3754 - accuracy: 0.8658
Epoch 3/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3374 - accuracy: 0.8771
Epoch 4/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3110 - accuracy: 0.8859
Epoch 5/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2935 - accuracy: 0.8903
Epoch 6/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2823 - accuracy: 0.8942
Epoch 7/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2682 - accuracy: 0.9002
Epoch 8/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2575 - accuracy: 0.9041
Epoch 9/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2479 - accuracy: 0.9074
Epoch 10/10
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2417 - accuracy: 0.9088
<tensorflow.python.keras.callbacks.History at 0x7f2b4a7cb7b8>
```
```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)

print('\nTest accuracy:', test_acc)
```
```
313/313 - 0s - loss: 0.3461 - accuracy: 0.8812

Test accuracy: 0.8812000155448914
```

La precisión en el Epoch 10 es 0.9088 y la precisión en el conjunto de prueba cuando se compara el modelo entrenado con el conjunto de test es 0.8812.


#### Pregunta 3

```python
model.fit(train_images, train_labels, epochs=20) # los epochs determinan cuántas veces se entrena un modelo
```
```
Epoch 1/20
1875/1875 [==============================] - 5s 3ms/step - loss: 0.4935 - accuracy: 0.8268
Epoch 2/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3769 - accuracy: 0.8639
Epoch 3/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3387 - accuracy: 0.8776
Epoch 4/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.3113 - accuracy: 0.8858
Epoch 5/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2966 - accuracy: 0.8903
Epoch 6/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2803 - accuracy: 0.8957
Epoch 7/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2679 - accuracy: 0.9008
Epoch 8/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2565 - accuracy: 0.9049
Epoch 9/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2475 - accuracy: 0.9083
Epoch 10/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2399 - accuracy: 0.9103
Epoch 11/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2298 - accuracy: 0.9141
Epoch 12/20
1875/1875 [==============================] - 3s 2ms/step - loss: 0.2235 - accuracy: 0.9163
Epoch 13/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2165 - accuracy: 0.9190
Epoch 14/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2105 - accuracy: 0.9206
Epoch 15/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.2035 - accuracy: 0.9240
Epoch 16/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.1978 - accuracy: 0.9253
Epoch 17/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.1918 - accuracy: 0.9285
Epoch 18/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.1877 - accuracy: 0.9286
Epoch 19/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.1820 - accuracy: 0.9313
Epoch 20/20
1875/1875 [==============================] - 4s 2ms/step - loss: 0.1762 - accuracy: 0.9335
<tensorflow.python.keras.callbacks.History at 0x7f90ac950550>
```

```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)

print('\nTest accuracy:', test_acc)
```
```
313/313 - 0s - loss: 0.3648 - accuracy: 0.8892

Test accuracy: 0.88919997215271
```

La precisión del último epoch, Epoch 20, es 0.9335 y la precisión en el conjunto de prueba cuando se compara el modelo entrenado con el conjunto de test es 0.8892.

#### Pregunta 4
Vemos una correlación positiva. A medida que aumentamos el número de epochs, hay más datos con los que entrenar el modelo, por lo que la precisión aumenta.

## Actividad 5
Para esta actividad, usaremos esta imagen.
```python
plt.figure()
plt.imshow(train_images[0]) # Muestra la primera imagen del conjunto de datos como un gráfico o píxeles de diferentes colores
plt.colorbar() # Muestra la barra de color a la derecha
plt.grid(False)
plt.show() # Muestra todo el gráfico
```
![Ankle Boot](../media/a2q1.png "Ankle Boot")

#### Pregunta 1
```python
probability_model = tf.keras.Sequential([model, tf.keras.layers.Softmax()])
```
```python
predictions = probability_model.predict(test_images)
```
```python
predictions[0] # Devuelve las probabilidades para la primera imagen; depende del índice
```
```
array([1.1623413e-08, 2.3745208e-08, 3.5589391e-08, 1.2773025e-09,
       5.3400743e-08, 2.0998505e-04, 7.4230536e-07, 6.9385571e-03,
       2.8271037e-07, 9.9285042e-01], dtype=float32)
```

![](https://i.imgur.com/td1b4Jk.png)

El índice 9 tiene el valor de confianza más alto, y el índice 1 tiene el valor de confianza más bajo.

#### Pregunta 2
```python
np.argmax(predictions[0]) # Esto devuelve el índice con la probabilidad más alta
```
```
9
```

```python
test_labels[0]  # Este es el valor de índice devuelto por el conjunto de prueba
                # (Con el que estamos comparando)
```
```
9
```

```python
class_names[9] # Este es el nombre de la categoría de la imagen que tiene la mayor probabilidad
```
```
'Ankle boot'
```


![](https://i.imgur.com/XeZoptk.png)

Esto corresponde a la categoría 'Ankle Boot'.

## Actividad 6
Para esta respuesta, usaremos esta imagen. Siéntete libre de usar cualquier imagen del conjunto de datos, pero asegúrate de ser coherente con los valores.
```python
plt.figure()
plt.imshow(train_images[7]) # Muestra la primera imagen del conjunto de datos como un gráfico o píxeles de diferentes colores
plt.colorbar() # Muestra la barra de color a la derecha
plt.grid(False)
plt.show() # Muestra todo el gráfico
```
![Shirt](../media/a2progress2.png "Shirt")

```python
probability_model = tf.keras.Sequential([model, tf.keras.layers.Softmax()])
```
```python
predictions = probability_model.predict(test_images)
```
```python
predictions[7] # Devuelve las probabilidades para la imagen en el índice 7; depende del índice
```
```
array([3.5166186e-06, 5.8611111e-12, 7.3947496e-04, 3.9665038e-06,
       2.8206115e-03, 9.7542063e-08, 9.9643230e-01, 8.2940481e-11,
       1.2411938e-07, 2.7266096e-09], dtype=float32)
```
El índice 6 tiene el valor de confianza más alto, y el índice 7 tiene el valor de confianza más bajo.

```python
np.argmax(predictions[7]) # Esto devuelve el índice con la probabilidad más alta
```
```
6
```

```python
test_labels[7]  # Este es el valor de índice devuelto por el conjunto de prueba
                # (Con el que estamos comparando)
```
```
6
```

```python
class_names[6] # Este es el nombre de la categoría de la imagen que tiene la mayor probabilidad
```
```
'Shirt'
```

Esto corresponde a la categoría 'Shirt'.

## Actividad 7

#### Pregunta 1
```python
# Toma una imagen del conjunto de prueba. Esto muestra la resolución de la imagen. 

#NOTA: Este índice se cambiará y su correspondiente gráfico se mostrará en los siguientes pasos
img = test_images[7]

print(img.shape)
```

```python
plot_value_array(7, predictions_single[0], test_labels)  # dibuja el gráfico que contiene todos los nombres de clase
_ = plt.xticks(range(10), class_names, rotation=45)
```
![Classification Plot](../media/PU3_graph.png "Classification Plot")



```python
i = 7   # Podemos ver que esta imagen detecta la clase correcta para la imagen
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```
![Image and Graph](../media/PU3_shirtandgraph.png "Image and graph")


Sí, esto es consistente con la pregunta anterior.

; mantenerlo claro para principiantes.
        Preserve los términos técnicos, la sintaxis del código y el formato. Solo traduce los comentarios que explican conceptos.
        Adapta las referencias culturales según sea apropiado. No traduzcas la clave del encabezado ni el HTML de las imágenes.