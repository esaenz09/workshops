---
title: "Activity 1: Create a color board"
prereq: "Python Basics, Python Image Manipulation: Open an Image, Python Pixels: Colors and Pixels"
difficulty: "Intermediate"
date: 2020-07-11T00:00:00Z
weight: 1
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/Nz3Uz4kBoUU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Ejemplo de tablero de colores básico

Aquí hay un ejemplo de cómo crear un tablero de colores con el color rojo, un ancho de 60 y una altura de 30.

```python
# Este es el ejemplo para crear un tablero de colores.
from PIL import Image
img = Image.new('RGB', (60, 30), 'red')
img.save('pil_red.png')
```
![alt text](../../media/whileloopbefore.png "image showing activity one first example")

## ¡Crea tu propio tablero de colores!

Elige tu color favorito y crea un tablero de colores para practicar. Aquí hay algunos colores de ejemplo que puedes elegir, pero también puedes escoger cualquier otro color.

<img src="../../media/Color-chart.png" width=30%>

<!-- Para accesibilidad, usa este HTML de etiqueta -->
<label for="colorpicker">Puedes usar el selector de color para elegir un color:</label>
<input type="color" id="colorpicker">

{{% notice warning %}}
 Para ver tu imagen, haz clic en la esquina superior izquierda (donde dice 'Files'), y luego haz clic en el archivo de imagen para ver el resultado.
<div style="width:100%">
    <table>
        <td>
            <img src="../../media/open-file1.png" width=100%>
        </td>
        <td>
            <img src="../../media/open-file2.png" width=100%>
        </td>
    </table>
</div>
{{% /notice %}}

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity1" target="_blank">Abrir Replit</a>