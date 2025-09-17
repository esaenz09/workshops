---
title: "Pixels on an Image"
draft: false
weight: 4
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/WvDHBwyM6_U" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Píxeles

Los píxeles son pequeñas áreas de color en una pantalla. Las imágenes se forman mediante píxeles en la pantalla. Podemos manipular los píxeles cambiando el valor **RGB**, que en esencia significa cambiar el valor de rojo, verde y azul en cada píxel. Cuando vemos una imagen en una pantalla, está compuesta por muchísimos píxeles diminutos en muchos colores uno al lado del otro. Sin embargo, cada píxel diminuto tiene un único color en una posición única dentro de la imagen.

<div style="width:80%;padding-left:20%;">
    <table>
        <td>
            <img src="../../media/nuvi.png" width=100%>
        </td>
        <td>
            <img src="../../media/pixel-nuvi.png" width=100%>
        </td>
    </table>
</div>

Vamos a empezar a crear imágenes. ¡No olvides que aprendimos a abrir y guardar imágenes en Python usando el módulo Pillow en las secciones anteriores!

## Crear imágenes usando píxeles

```python
# Recuerda importar Image
from PIL import Image

Image.new(mode, size)
Image.new(mode, size, color)
```

`Image.new()` crea una nueva imagen con el modo y el tamaño indicados (y opcionalmente, el color). Aquí podemos usar `RGB` como modo. El tamaño es un valor `(width, height)` de una imagen. El color es el color RGB de los píxeles. También podemos usar nombres de colores en lugar de valores RGB. Si no inicializas el valor de color, la imagen se rellena de negro.

## Veamos algunos ejemplos

```python
# Recuerda importar Image
from PIL import Image
img = Image.new('RGB', (200,100),(100,100,100))
img.save('pil_grey.png')
```
La variable `img` guarda la imagen PNG que se ve así: 

![alt text](../../media/grey.png "Image showing pixels first example")

```python
# Recuerda importar Image
from PIL import Image
img=Image.new('RGB', (200,100),"black")
img.save('pil_black.png')
```
Aquí, especificar `black` como color RGB crea y guarda la imagen PNG que se ve así:

![alt text](../../media/black.png "Image showing pixels second example")

## Cambiar un píxel en una imagen

¿Qué pasa si queremos poner otro píxel en una imagen?

La función `img.putpixel( (x,y), (r, g, b))` coloca un nuevo píxel en la imagen con la posición y el color dados. La posición es un valor `(width, height)` de la ubicación de ese píxel en la imagen. El color es el color RGB de ese píxel.

## Veamos un ejemplo

```python
# Recuerda importar Image
from PIL import Image
img=Image.new('RGB', (200,100),"yellow")
img.putpixel( (100,50), (0, 0, 0))
img.save('pil_black-dot.png')
```

Después de crear una imagen amarilla de 200x100, la función `putpixel` coloca un pequeño punto en el centro de este bloque amarillo. Es un píxel muy pequeño; de hecho, ¡es tan pequeño que puede que tengas que ampliar la imagen para verlo!

![alt text](../../media/black-dot.png "image showing pixels third example")