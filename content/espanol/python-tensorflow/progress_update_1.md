---
title: "Progress Update 1"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists"
difficulty: Intermediate
weight: 4
draft: false
---

## Compara tu código

Antes de continuar, por favor compara tu cuaderno de Google Colab con el código siguiente:

```python
# Importando TensorFlow y la biblioteca tf.keras
import tensorflow as tf
from tensorflow import keras 
```

```python
# Esta variable se obtiene del conjunto de datos fashion_mnist
fashion_mnist = keras.datasets.fashion_mnist 
```

```python
# Esto carga cuatro variables del conjunto de datos.
# train_images y train_labels son los datos que el modelo usa para aprender
# test_images y test_labels son usados por el modelo para comparar
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
```

```python
class_names = ['T-shirt/top', 'Trouser', 'Pullover', 'Dress', 'Coat', 'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot'  ]
```

```python
# Muestra la primera imagen del conjunto de datos como un gráfico (píxeles con distintos colores)
plt.figure()
plt.imshow(train_images[0]) # Muestra la primera imagen del conjunto de datos como un gráfico (píxeles con distintos colores)
plt.colorbar() # muestra la barra de colores a la derecha
plt.grid(False)
plt.show() # muestra el gráfico
```

![Ankle Boot](../media/a2q1.png "Pixelated boot with color bar")

```python
# Muestra la octava imagen del conjunto de datos como un gráfico (píxeles con distintos colores)
plt.figure()
plt.imshow(train_images[7]) # Muestra la octava imagen del conjunto de datos como un gráfico (píxeles con distintos colores)
plt.colorbar() # muestra la barra de colores a la derecha
plt.grid(False)
plt.show() # muestra el gráfico
```

![Shirt](../media/a2progress2.png "Pixelated shirt with color bar")

```python
# train_images y test_images tienen valores entre 0 y 255.
# Para mantener la consistencia entre los conjuntos de entrenamiento y prueba, dividimos train_images y test_images por 255
train_images = train_images / 255.0 
test_images = test_images / 255.0
```

{{% notice info %}}

Si deseas probar el código anterior, visita <a href="https://colab.research.google.com/drive/1ndj0W1P_3uAG-L2a6LwxdJPSHbSK5WE6?usp=sharing" target="_blank">este enlace</a>

Para editar este código, haz clic en el botón 'Copy to Drive' para crear una copia personal de este notebook. Asegúrate de haber iniciado sesión en tu cuenta de Google.
![Screenshot of Google Colab Notebook with "Copy to Drive button selection highighted"](../media/colab_copy.png "Screenshot of Google Colab Notebook ")

{{% notice warning %}}
### Si estás usando temporalmente una cuenta nueva de Google
Una vez que hagas una copia, asegúrate de reemplazar "Copy of" por tu nombre en el nombre del archivo. Esto aparece en la esquina superior izquierda del notebook.
{{% /notice%}}

{{% /notice %}}; manteniéndolo claro para principiantes.