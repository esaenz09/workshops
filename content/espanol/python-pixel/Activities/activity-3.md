---
title: "Activity 3: Challenge: Design new elements"
prereq: "Python Basics, Python Image Manipulation: Open an Image, Python Pixels: Colors and Pixels"
difficulty: "Intermediate"
date: 2020-09-08T00:00:00Z
weight: 3
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/YkxNH1TWjR0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Usando bucles, en realidad puedes diseñar tus propios elementos en el colorboard. Puedes diseñar tu propio logo o cualquier cosa que quieras en este colorboard. Aquí tienes un ejemplo que te hemos proporcionado.


### Ejemplo: crea una N.

```python
# Esto crea el colorboard original.
from PIL import Image
img = Image.new('RGB', (60, 30), 'white')

# Esto usa bucles anidados para cambiar el colorboard.
# Línea vertical izquierda
for x in range(10, 15):
  for y in range(5, 25):
    img.putpixel( (x,y), (0, 0, 0))

# Línea vertical derecha
for x in range(30, 35):
  for y in range(5, 25):
    img.putpixel( (x,y), (0, 0, 0))

# Línea diagonal central
for y in range(5, 25):
  for x in range(10+(y-5), 15+(y-5)):
    img.putpixel( (x,y), (255, 211, 0)) 
img.save('pixel-activity3.png')
```
output:
![alt text](../../media/Activity3_ex.png "image showing activity3 example") 


### ¡Diseña tu propio elemento!

{{% notice tip %}}
En realidad puedes diseñar algunas letras sencillas, como H, K, T, etc. Puedes cambiar el color de ciertas partes de esas letras para que queden más bonitas.
{{% /notice %}}

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Python-Pixel-Activity3" target="_blank">Abrir Replit</a>