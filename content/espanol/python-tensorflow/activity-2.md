---
title: "Activity 2 - Displaying RGB Color Values for Images"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists"
difficulty: Intermediate
weight: 3
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/bMr1c4a7dXQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Ver imágenes de las muestras

Ahora vamos a ver la imagen de un zapato de nuestra colección de muestras de ropa usando el fragmento de código que aparece a continuación.

Copia el siguiente código en tu cuaderno de Google Colab:

```python
plt.figure()
plt.imshow(train_images[0]) # Muestra la primera imagen del conjunto de datos como una gráfica de píxeles de diferentes colores
plt.colorbar() # Muestra la barra de colores a la derecha
plt.grid(False)
plt.show() # Muestra la gráfica completa
```

{{% notice tip %}}

Fíjate que la imagen generada tiene una barra de colores a la izquierda. Esta métrica muestra que el zapato usa valores de píxeles de 0 a 255. ¿Qué son los valores de píxeles?

Los píxeles son la unidad más pequeña de una gráfica (imagen o pantalla) que un monitor puede representar. ¡Piensa en la pantalla de tu ordenador! Hay millones de pequeños puntos de color que, al combinarse, pueden crear la imagen de un bote o el texto que ves en la pantalla.

La barra de colores muestra el rango en la intensidad del color que un píxel puede mostrar.
![Imagen de bota con rango de pixelación de 0 a 255](../media/a2q1.png "Bota pixelada con barra de color")
{{% /notice %}}

#### Pregunta 1:
Después de analizar el zapato, queremos ver otro artículo de la muestra de ropa. ¿Puedes averiguar cómo hacerlo usando el bloque de código anterior?

{{% notice hint %}}
Usa el código del bloque anterior. Luego cambia el valor del índice en `train_images[x]` para obtener una nueva imagen de un artículo.

Por ejemplo, si pones el valor de índice 7, obtendrás el siguiente artículo:
![Imagen de camiseta](../media/a2progress2.png "Camiseta pixelada con barra de color")
{{% /notice %}}

### Normalizar valores de píxeles:

El programa que vamos a escribir toma entradas con valores entre 0 y 1. Sin embargo, nuestros valores de píxeles son en su mayoría mayores que 1. De hecho, el rango de valores es de 0 a 255. ¿Cómo podemos cambiar el rango de números para que pueda ser usado como entrada en nuestro programa?

Usaremos un proceso llamado "normalización", donde transformamos estos valores para que entren en el rango de 0 a 1. Más específicamente, tomaremos todos nuestros datos y los dividiremos por un valor único para que el rango de valores ahora quepa entre 0 y 1.

#### Pregunta 2:
¿Puedes adivinar por qué número vamos a dividir nuestros valores para normalizar el rango?

{{% notice tip %}}
Si esto te confunde, piensa en porcentajes. Si tienes un examen que se califica sobre 255 puntos y obtienes 240 puntos correctos, divides 240 entre 255 para obtener el porcentaje que conseguiste. Estamos haciendo un proceso similar aquí.
{{% /notice %}}

Copia y pega el siguiente bloque de código en tu cuaderno de Google Colab:

```python
# train_images y test_images tienen valores en el rango de 0 a 255.
# Para mantener la consistencia entre el conjunto de entrenamiento y el de prueba, dividiremos train_images y test_images por 255

train_images = train_images / 255.0 

test_images = test_images / 255.0
```