---
title: "Haz Que el Pájaro Salte y Añade Gravedad"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
---

### ¿Qué deberíamos hacer con el pájaro?

Hagamos que salte:

Agrega el siguiente comando en el archivo [File: create-game.js]
     spaceKey.onDown.add(jump, this);

### Trabajando juntos

En la ventana de Replit de abajo, comenzamos el código con la línea `spaceKey.onDown.add(jump, this);`.

![alt text](../img/jump.png "image to add jump down")

En la consola deberías ver un Jsappy bird saltando después de presionar **run**:

![alt text](../img/jump_output.png "Image of jumping bird")

## Añadir gravedad
### Trabajando juntos

En la ventana de Replit de abajo, iniciamos el código con la línea `bird.body.gravity.y = 900;`.

![alt text](../img/gravity.png "image to add gravity to the bird")

En la consola deberías ver un JSappy bird saltando con gravedad después de presionar **run**:

![alt text](../img/jump_output.png "bird jumping with gravity")
