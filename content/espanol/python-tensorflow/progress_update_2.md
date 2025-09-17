---
title: "Progress Update 2"
date: 2020-03-27T20:24:33-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists, Tuples, Sets; Loops- For Loops"
difficulty: Intermediate
weight: 10
draft: false
---

¡Buen trabajo! Ahora puedes identificar con éxito a qué categoría pertenece con mayor probabilidad una imagen.

Para verificar que tu código es correcto hasta este punto de control, por favor compara tu código con el ejemplo provisto a continuación.

{{% notice warning %}}
Las salidas del código pueden variar. Solo necesitas copiar los bloques de código, y __no__ los bloques de salida, ya que se generarán automáticamente en tu cuaderno.
{{% /notice %}}

## Compara tu código

Antes de continuar, por favor revisa tu cuaderno de Google Colab comparándolo con el código que sigue:

```python
plt.figure(figsize=(10,10)) #establece el tamaño de la imagen a 10x10 píxeles
for i in range(25): #muestra las primeras 25 imágenes con el nombre de su clase
    plt.subplot(5,5,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary) 
    plt.xlabel(class_names[train_labels[i]])
plt.show() #muestra las imágenes con sus etiquetas

```
![clothing sample images, 5x5](../media/PU2_25images.png "Clothing sample images")

```python
#Construyendo la red neuronal
model = keras.Sequential([ 
    keras.layers.Flatten(input_shape=(28, 28)), 
    keras.layers.Dense(128, activation='relu'),
    keras.layers.Dense(10)
])
```

```python
model.compile(optimizer='adam',
              loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])
```

```python
model.fit(train_images, train_labels, epochs=10) 
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
313/313 - 0s - loss: 0.3358 - accuracy: 0.8825

Test accuracy: 0.8824999928474426
```

```python
probability_model = tf.keras.Sequential([model, tf.keras.layers.Softmax()])
```

```python
predictions = probability_model.predict(test_images)
```

```python
predictions[7] #Devuelve las probabilidades para cada clase; el índice con mayor probabilidad depende del valor del índice.
```

```
array([3.5166186e-06, 5.8611111e-12, 7.3947496e-04, 3.9665038e-06,
       2.8206115e-03, 9.7542063e-08, 9.9643230e-01, 8.2940481e-11,
       1.2411938e-07, 2.7266096e-09], dtype=float32)
```

```python
np.argmax(predictions[7]) # Esto devuelve el índice con la mayor probabilidad
```

```
6
```

```python
test_labels[7]  # Este es el valor del índice proporcionado por el conjunto de datos de prueba
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

Ahora que podemos clasificar la categoría de una prenda individual usando tu modelo, visualizaremos estas predicciones creando un gráfico de barras para una imagen específica.

{{% notice info %}}

Si quieres probar el código anterior, visita <a href="https://colab.research.google.com/drive/1knoCeFRtcUbp1HyKKEQgYw9tgZsUeDk0?usp=sharing" target="_blank">este enlace</a>

Para editar este código, haz clic en el botón 'Copy to Drive' para hacer una copia personal de este cuaderno. Asegúrate de haber iniciado sesión en tu cuenta de Google.

{{% notice warning %}}
### Si estás usando temporalmente una cuenta nueva de Google
Una vez que hagas una copia, por favor asegúrate de reemplazar "Copy of" con tu nombre, junto con el nombre del archivo. Esto aparecerá en la esquina superior izquierda de tu cuaderno.
{{% /notice %}}

{{% /notice %}}