---
title: "Basics of colors"
draft: false
weight: 3
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/-ior2GcSYa4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Fundamentos de los colores
Mientras revisas todo tipo de imágenes en línea, ¿alguna vez te has preguntado cómo esas imágenes obtienen sus colores? En realidad, los ordenadores tienen el modo *RGB* para representar colores.

## Formato RGB
En Python, seguimos un formato específico al definir colores:
(R, G, B), donde "R", "G" y "B" son todos enteros. "R" representa cierta cantidad de <span style="color:red; font-weight:bold"> rojo</span>, "G" representa cierta cantidad de <span style="color:green; font-weight:bold"> verde</span>, y "B" representa cierta cantidad de <span style="color:blue; font-weight:bold"> azul</span>.

El color representado por (R, G, B) es lo que obtenemos de "la mezcla de" diferentes cantidades de rojo, verde y azul.

<!-- Para accesibilidad, utiliza esta etiqueta label HTML -->
<label for="colorpicker">Puedes hacer clic en la línea de abajo y elegir los colores que quieras en el panel de colores para observar sus valores RGB:</label>
<input type="color" id="colorpicker">

{{% notice tip %}}
*¿Qué queremos decir con la "mezcla de colores"?*

Aquí estamos usando diferentes cantidades de luz roja, verde y azul para obtener un nuevo color de luz. Igual que usamos diferentes cantidades de pigmentos al pintar, estamos mezclando diferentes cantidades de luces para crear distintos colores de luz. Los pigmentos usan los colores primarios rojo, amarillo y azul, mientras que los ordenadores usan colores primarios de luz rojo, verde y azul.

Esta imagen representa, de forma muy aproximada, cómo se mezclan los colores:
![alt text iframe height="600px" width="40%"](../../media/colors.svg.png "color representation")

Al igual que no debemos usar demasiado pigmento, también hay una limitación para representar colores. El entero máximo que podemos usar para representar cada cantidad de color es 255 y el entero mínimo que podemos usar para representar cada cantidad de color es 0. Esto está definido en el modo RGB.

En todo el material siguiente, "color" significa "el color de la luz".
{{% /notice %}}


## Preguntas y respuestas
1. ¿Qué color representa (0, 0, 0)?

<center>
<label for="colorpickerQ1">Pruébalo:</label> </br>
<input type="color" id="colorpickerQ1"
style="display:inline-block;width:40%;height:100px;">
</center>

{{% showanswer "Mostrar respuesta" %}}
Negro. Todos los colores están al 0%. (No hay color aquí. ¡Todo está oscuro. Es negro!)
![alt text height="600px" width="40%"](../../media/black.png "black")
</br>
{{% /showanswer %}}

2. ¿Qué color representa (255, 255, 255)?

<center>
<label for="colorpickerQ2">Pruébalo:</label> </br>
<input type="color" id="colorpickerQ2"
style="display:inline-block;width:40%;height:100px;">
</center>

{{% showanswer "Mostrar respuesta" %}}
Blanco. 255 representa que estás usando el 100% de cada color, lo cual está saturado. (Cuando todos los colores están saturados, obtienes blanco)
![alt text height="600px" width="40%"](../../media/white.png "white")
</br>
{{% /showanswer %}}

3. ¿Qué color representa (100, 100, 100)?

<center>
<label for="colorpickerQ3">Pruébalo:</label> </br>
<input type="color" id="colorpickerQ3"
style="display:inline-block;width:40%;height:100px;">
</center>

{{% showanswer "Mostrar respuesta" %}}
Gris. 100 / 255 ≈ 39.2%. Obtendrás gris al sumar 39.2% de rojo, 39.2% de azul y 39.2% de verde.
![alt text height="600px" width="40%"](../../media/grey.png "gray")
</br>
{{% /showanswer %}}

*Nota: No te asustes si te sientes confundido aquí; explicaremos más sobre estas ideas con actividades en código Python más adelante en el taller.*
<br/><br/>

## Colores incorporados

En Python, la mayoría de los colores más usados ya están preparados para ti. Cuando necesites referirte a un color, simplemente haz:
```python
color = 'color name'
```
Por ejemplo:
Rojo:
```python
color = 'red'
# El siguiente código se usa para mostrarte el color que obtienes.
# Puedes omitir estas líneas por ahora y las explicaremos en la página siguiente.
img = Image.new('RGB', (60, 30), color)
img.save('red.png')
img.show('red.png')
```
Lo siguiente es tu salida:
![alt text](../../media/whileloopbefore.png "red")
¡Asombroso! ¡Obtienes rojo!
; mantenerlo claro para principiantes.
        Preservar términos técnicos, sintaxis de código y formato. Solo traduce los comentarios que expliquen conceptos.
        Adaptar las referencias culturales apropiadamente. No traduzcas la clave de encabezado title; no traduzcas el HTML de las imágenes.