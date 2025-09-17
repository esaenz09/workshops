---
title: "The Menu"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
---

<p style="text-align: center;"><iframe width="60%" height="600px" src="https://youtube.com/embed/LelFnKtml8Q" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## Almacenando información del restaurante

Let's recall the restaurant array that we made earlier in the array section. 

![restaurant](../../arrays/img/array2.png)

Como puedes ver, este array contiene todos los restaurantes diferentes para nuestra app. Ahora, intentemos hacer que cada restaurante contenga un array con todos sus elementos del menú. Si se hace correctamente, el elemento `0` de nuestro array, "Burger King", debería ahora contener sus elementos del menú correspondientes. Podría verse algo así:

![burgerkingarray](../img/2darray2.png)

Como puedes ver, el elemento `0` debería ser nuestro array de Burger King. Al igual que con nuestros 1D arrays, indexamos los ítems empezando en cero. Si quisiéramos hacer un pedido de un Whopper, simplemente llamaríamos a `Restaurant[0][0]`. Esto llamaría al array de Burger King y al primer elemento de ese array, que es un Whopper. Si quisiéramos papas fritas en nuestro array, entonces llamaríamos a `Restaurant[0][2]`. 

Pregunta: Si quisiéramos pedir orange chicken y orange chicken fuera el décimo elemento de nuestro array de Panda Express, ¿cómo podríamos acceder a ese elemento?

Si respondiste `Restaurant[2][9]`, ¡entonces estás en lo correcto! Panda Express es el tercer array `[2]`, y orange chicken es el décimo elemento `[9]`. Esto se mantiene claro para principiantes.