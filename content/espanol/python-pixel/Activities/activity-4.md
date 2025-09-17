---
title: "Activity 4: Create Basic Filter"
date: 2020-09-08T00:00:00Z
prereq: "Python Basics, Python Pixels: Colors and Pixels, Python Image manipulation: Open an image"
difficulty: "Intermediate"
weight: 4
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/jA6xNqAhb1o" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Ahora que entendemos más sobre píxeles e imágenes, podemos empezar a aprender a diseñar tu propio filtro en la imagen. Veamos algunos ejemplos de cómo diseñar un filtro básico en tu imagen.

### Ejemplo de filtro azul

<img src="../../media/cat.png" width=50%>
Queremos añadir un filtro azul al lindo gato de arriba. Veamos cómo lograrlo.

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")

# Añadamos el filtro azul
for i in range(img.size[0]): # Para cada columna
    for j in range(img.size[1]): # Para cada fila
        color = img.getpixel( (i,j) )
        img.putpixel((i,j),(0, 0, color[2])) # Establecer el color en consecuencia

# Guardar el gato después del filtrado
img.save("Mycat.png")
```

¡Guau! Este es nuestro gato después del filtro azul.
<img src="../../media/bluefiltercat.png" width=50%>

{{% notice tip %}}
¿Cómo funcionó esto? Veamos el bucle: 

```python
for i in range(img.size[0]): # Para cada columna
    for j in range(img.size[1]): # Para cada fila
        color = img.getpixel( (i,j) ) # Obtener el píxel actual
        img.putpixel((i,j),(0, 0, color[2])) # Establecer el color en consecuencia
```

Comenzamos recorriendo la imagen, por cada columna y cada fila, para obtener cada píxel. Luego obtiene el valor de color actual del píxel. Para aplicar un filtro azul a ese píxel, lo único que hacemos es poner los valores RGB de 'Rojo' y 'Verde' en 0. Por lo tanto, solo quedan los valores de 'Azul'. 

{{% /notice %}}


### Desafío - Crea tu propio filtro

Siguiendo el ejemplo anterior, intenta crear tus propios filtros con diferentes colores.
<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity4" target="_blank">Launch Replit</a>

Finalmente, piensa e intenta crear un filtro en escala de grises. Hablaremos sobre cómo crear un filtro en escala de grises en la siguiente sección.