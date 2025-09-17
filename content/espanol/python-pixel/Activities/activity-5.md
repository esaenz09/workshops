---
title: "Activity 5: More advanced filters"
date: 2020-09-08T00:00:00Z
prereq: "Python Basics, Python Pixels: Colors and Pixels, Python Image manipulation: Open an image"
difficulty: "Intermediate"
weight: 5
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/deYXkPt58co" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  
  
En la sección anterior vimos un ejemplo de cómo crear un filtro azul y pensamos en cómo crear el filtro gris. Ahora, vamos a crear juntos nuestro filtro gris.

### Ejemplo - Crear un filtro gris

¡Cambiemos la imagen original del gato de abajo con nuestro filtro gris juntos!

<img src="../../media/cat.png" width=50%>

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de los píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")

# Filtro gris
for i in range(img.size[0]): # Para cada columna:
    for j in range(img.size[1]): # Para cada fila
        color = img.getpixel( (i,j)) # Obtener el color
        GREY = (color[0] + color[1] + color[2]) // 3 # Promediar los valores del píxel
        img.putpixel((i,j),(GREY, GREY, GREY)) # Establecer el color en consecuencia

# Guardar el gato después del filtrado
img.save("Mycat.png")
```

{{% notice tip %}}
Recuerda: para establecer un píxel gris los tres valores de RGB deben ser iguales. Sin embargo, fijar cada píxel al mismo valor aleatorio (p. ej., 200) hará que toda la imagen sea gris, en lugar de simplemente añadir un filtro sobre la imagen existente del gato.

¿Cómo podemos determinar la mejor manera de establecer un píxel como su versión "grisada"? Podemos tomar el promedio de cada valor de los colores RGB. Puedes usar // para hacer una división entera, lo que garantiza que el resultado de la operación de promedio sea un número entero.
{{% /notice %}}

¡Guau! Este es nuestro gato después del filtro gris.
  
<img src="../../media/greyfiltercat.png" width=50%>

### Ejemplo - Filtro parcial

Ahora, pensemos en cómo añadir un filtro solo en parte de nuestro adorable gato.

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de los píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")

# Filtro gris
for i in range((img.size[0] // 2)): # Para las columnas de la primera mitad
    for j in range((img.size[1] // 2)): # Para las filas de la primera mitad
        color = img.getpixel((i,j)) # Obtener el color
        GREY = (color[0] + color[1] + color[2]) // 3 # Promediar los valores del píxel
        img.putpixel((i,j),(GREY, GREY, GREY)) # Establecer el color en consecuencia

# Guardar el gato después del filtrado
img.save("Mycat.png")
```

¡Vaya! Este es nuestro gato después del filtro. ¡Solo filtramos una cuarta parte del gato en la esquina superior izquierda!

<img src="../../media/partialfilter.png" width=50%>

### Desafío - Crea tu propio filtro parcial

¡Ahora es tu turno de filtrar la parte que quieras con distintos tipos de filtros en el lindo gato! ¡Emocionante!

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity5" target="_blank">Abrir Replit</a>

{{% showanswer Advanced %}}

¿No sería genial si pudiéramos tomar los pasos anteriores y simplificarlos? Hagámoslo usando las funciones `filter()` y `convert()` del módulo ImageFilter de Pillow.

Para usar la función `filter()`, puedes especificar el tipo de ImageFilter entre paréntesis. Por ejemplo, `image.filter(ImageFilter.BLUR)` volverá la imagen borrosa. O, si usas `ImageFilter.CONTOUR`, añadirá un efecto tipo “boceto” a tu imagen.

Por ejemplo, para la 'img' anterior:

```python
    blurredImage = img.filter(ImageFilter.BLUR) 
    blurredImage.save("myCatBlurred.jpg")
```

Deberías ver que la imagen guardada del gato está borrosa. ¡Prueba esto con varios filtros de imagen hasta que encuentres uno que te guste!

Adicionalmente, podemos usar la función `convert()` para poner nuestra imagen en blanco y negro. Para usar esta función, puedes especificar el modo al que quieres convertir la imagen. Los modos más comunes son "L", que convierte una imagen a escala de grises, y "RGB", que convierte una imagen a color real.

Probémoslo así:

```python
    greyscaleImage = img.convert("L")
    greyscaleImage.save("myCatBW.jpg")
```

Si combinas la función de desenfoque y la conversión a blanco y negro, obtendrás algo así – ¡purrfect!

<img src="../../media/bw_upside_down.png" alt="blurred black and white cat upside down" width=50%>
</br>
{{% /showanswer %}}