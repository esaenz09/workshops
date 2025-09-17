---
title: "Activity 9: Rotate your image"
date: 2020-09-08T00:00:00Z
prereq: "Python Basics, Python Pixels: Colors and Pixels, Python Image manipulation: Open an image"
difficulty: "Intermediate"
weight: 9
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/m0d9NT0MEPE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

En esta sección, empezaremos a aprender cómo rotar tu imagen usando píxeles.

### Ejemplo - Rota tu imagen 180 grados en sentido horario

Rotemos nuestro gato 180 grados en sentido horario.
<img src="../../media/cat.png" width=50%>

```python
# Necesitamos importar el paquete PIL para permitir la manipulación de píxeles.
from PIL import Image

# Abrir la imagen del gato
img = Image.open("cat.png")
width = img.size[0]
height = img.size[1]

# Crear una nueva imagen con el mismo ancho y alto
newimg = Image.new('RGB',(width,height) )

# Establecer el píxel para la nueva imagen
for i in range(width): # Por cada columna
    for j in range(height): # Por cada fila
        # Fíjate en cómo obtenemos heightNew.
        heightNew = height - 1 - j
        
        # Fíjate en cómo obtenemos widthNew.
        widthNew = width - 1 - i

        color = img.getpixel((widthNew, heightNew)) # Obtener el color de la imagen original
        newimg.putpixel((i,j),color) # Poner el color en la nueva imagen

newimg.save("Mycat.png")
```

¡Guau! Este es nuestro nuevo gato después de rotarlo.
<img src="../../media/catrot.png" width=50%>

{{% notice note %}}

Fíjate en cómo obtenemos heightNew y widthNew. Piensa en esas variables detenidamente e intenta visualizarlas.

Por ejemplo, intenta aplicarlas al siguiente grupo de letras 4x4:

<img src="../../media/table.png" width=15%>

Luego rótalo 180 grados en sentido horario y compáralo con la salida anterior. ¿Son iguales?
{{% /notice %}}


### Desafío - Rota tu gato 90 grados en sentido antihorario

¡Ahora es tu turno de rotar tu gato 90 grados en sentido antihorario!

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity9" target="_blank">Abrir Replit</a>

{{% showanswer Advanced %}}

El módulo Pillow tiene funciones que pueden ayudar a simplificar los pasos anteriores. Para eso, veamos la función `rotate()` de `Pillow Image`.

La rotación de imagen funciona usando ángulos. Por ejemplo, `rotate(45)` inclinará tu imagen 45 grados. Usar `rotate(90)` girará tu imagen 90 grados.

¡Probémoslo! Rota la imagen antes de guardarla:

```python
    image = Image.open("cat.jpg")
    image.rotate(90)
    image.save("myCat.jpg")
```

Hmm, la imagen no parece haberse rotado. ¿Por qué? Bueno, la imagen que abrimos se guarda en la variable image. Cuando rotamos la imagen, no guardamos la imagen rotada en ninguna variable, así que nuestro código no guarda la imagen rotada.

Hagámoslo así en su lugar:

```python
    image = Image.open("cat.jpg")
    image = image.rotate(90)
    image.save("myCat.jpg")
```

Desafío: ¿puedes darle la vuelta completa a esta imagen? ¿Puedes girarla 3/4 de vuelta sin usar un ángulo > 180? (Pista: ¡prueba usar números negativos para el ángulo!)

Girado totalmente, mi imagen se ve así:

<img src="../../media/upside_down.png" alt="cat upside down" width=50%>
</br>
{{% /showanswer %}}