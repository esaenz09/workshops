---
title: "Activity 10: Making a meme!"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 10
prereq: "Python Basics, Python Pixels: Colors and Pixels, Python Image manipulation: Open an image"
difficulty: "Intermediate"
--- 

Otra cosa que podemos hacer para mejorar nuestra imagen es añadir texto. Podemos hacerlo utilizando el módulo `Pillow ImageDraw`. Importémoslo al principio de nuestro archivo junto con las otras declaraciones de importación.

```python
    from PIL import Image
    from PIL import ImageFilter
    from PIL import ImageDraw
```

Para poder añadir texto, debemos volver a dibujar la misma imagen que usamos antes. Hagámoslo usando la función `draw()`, que recibe un objeto imagen. Una vez que la imagen está dibujada, podemos añadir texto a ella utilizando el método `text()` para establecer el texto de la imagen. El texto se dibuja según las coordenadas proporcionadas. La función toma dos parámetros obligatorios: las coordenadas xy y el texto.

Por ejemplo:

```python
    drawnImage = ImageDraw.Draw(img)
    drawnImage.text((200,20), "When you realize you learned python in an hour.")
    drawnImage.save("myCatWithText.jpg")
```


Mi imagen ahora se ve así:
<img src="../../media/meme.png" alt="blurred black and white cat upside down with text that says `when you realize you learned python in an hour.`" width=50%>

### Desafío - Cambiar la fuente
Puedes ver que el texto en la imagen creada arriba está en una fuente pequeña y predeterminada. Hay otros parámetros dentro del método `text()` que puedes usar. Consulta la [documentación](https://pillow.readthedocs.io/en/stable/reference/ImageDraw.html#PIL.ImageDraw.PIL.ImageDraw.ImageDraw.text) y averigua si puedes cambiar la fuente y el tamaño de la fuente, así como el color del texto! 

{{% notice note %}}

Esto requerirá descargar un archivo .ttf (también conocido como archivo de fuente) desde Internet. Pide ayuda si tienes alguna pregunta.

{{% /notice %}}