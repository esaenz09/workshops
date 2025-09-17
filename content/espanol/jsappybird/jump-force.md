---
title: "Make the bird jump with force & falling with rotation"
date: 2020-07-29T13:24:17-07:00
draft: false
weight: 4
---

Vamos a añadir fuerza al pájaro

Agrega el siguiente comando en el archivo [File: create-game.js]
    bird.body.velocity.y = -350;
    
{{% notice tip %}}

## Trabajando juntos

En la ventana de Replit más abajo, iniciamos el código con la línea `bird.body.velocity.y = -350;`.

![alt text](../img/jump_force.png "image to add gravity to the bird")

En tu consola deberías ver un JSappy bird saltando con fuerza después de presionar **run**:

![alt text](../img/jump_output.png "bird jumping with gravity")

{{% /notice %}}

## Actividad adicional

Hagamos que el pájaro salte hacia arriba y hacia adelante:

Agrega el siguiente comando en el archivo [File: create-game.js]
    bird.body.velocity.x = 100;

# Pájaro cayendo con rotación

Añadamos rotación al pájaro:

Agrega el siguiente comando en el archivo [File: update-game.js]
    if (bird.angle < 50) {
       bird.angle += 1;
    }

## Comentarios:

`If` es un bloque condicional donde comprobamos el ángulo del pájaro y, si es menor que 50, ejecutamos la condición.
   -bird.angle+=1;

{{% notice tip %}}

## Trabajando juntos

En la ventana de Replit más abajo, comenzamos el código con la línea `bird.angle +=1;`.

![alt text](../img/rotate.png "image to add rotation to the bird")

En tu consola deberías ver un Jsappy bird rotando con un ángulo después de presionar **run**:

![alt text](../img/rotate_output.png "bird rotating")

{{% /notice %}}

; manténlo claro para principiantes.