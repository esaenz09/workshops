---
title: "Activity 6: Crop Image"
prereq: "Fundamentos de Python, Manipulación de imágenes en Python: Abrir una imagen, Python Pixel: Colores y píxeles"
difficulty: "Intermedio"
date: 2020-09-08T00:00:00Z
weight: 6
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/X2AoHSdQOLo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

En esta sección, comenzaremos a aprender cómo recortar tu imagen.

### Ejemplo - Recortar el gato por la mitad

Ahora, recortemos la mitad derecha de la imagen del gato.
  
<img src="../../media/cat.png" width=50%>

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")
width = img.size[0] 
height = img.size[1] 

# Crear una nueva imagen con la mitad del ancho y la misma altura
newimg = Image.new('RGB', (width // 2, height))

# Establecer los píxeles para la nueva imagen
for i in range(width // 2):    
    for j in range(height): # Para cada fila
        color = img.getpixel((i,j)) # Obtener el color de la imagen original
        newimg.putpixel((i,j),color) # Poner el color en la nueva imagen

newimg.save("Mycat.png")
```

¡Guau! Este es nuestro gato después del recorte. ¡Hemos recortado la mitad derecha de la imagen!

<img src="../../media/halfcat.png" width=25%>

### Ejemplo - Recortar la parte central

Vamos a recortar la imagen del gato para quedarnos solo con la parte central!

<img src="../../media/cat.png" width=50%>

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")
width = img.size[0]
height = img.size[1]

# Crear una nueva imagen con la mitad del ancho y la mitad de la altura
newimg = Image.new('RGB', (width // 2, height // 2))

# Establecer los píxeles para la nueva imagen
for i in range(width // 4, (width // 4) * 3): # Seleccionar desde el primer cuarto hasta el tercer cuarto del ancho
    for j in range(height // 4, (height // 4) * 3): # Para cada fila (desde el primer cuarto hasta el tercer cuarto de la altura)
        color = img.getpixel((i,j)) # Obtener el color de la imagen original
        newimg.putpixel((i - width // 4, j - height // 4), color) # Poner el color en la nueva imagen (ajustando las coordenadas)

newimg.save("Mycat.png")
```

¡Guau! Este es nuestro gato después del recorte.
<img src="../../media/cropcat.png" width=25%>

### Desafío - Recorta la imagen según tu elección

Ahora es tu turno de recortar la parte que quieras del adorable gato. ¡Diviértete!
<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity6" target="_blank">Abrir Replit</a>