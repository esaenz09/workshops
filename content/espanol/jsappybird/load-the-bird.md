---
title: "Cargar La Imagen del Pájaro y Cambiar el Texto en la Pantalla"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
---

Primero, carguemos a Flappy y pongámoslo en la pantalla.

Add below command in the file [File: load-sprites.js]
      ```
      game.load.image('bird','assets/bird.png');
       ```
       
### Trabajando juntos

En la ventana de Replit más abajo, empezamos el código con la línea `game.load.image('bird', 'assets/bird.png');`.

![alt text](../img/loadbird.png "image to add the bird in the file")

En la consola verás un pájaro Jsappy después de pulsar **run** y luego la barra espaciadora:

![alt text](../img/loadbird_output.png "bird image in the output")

## Cambiar el texto de la pantalla

Cambiemos el texto de la pantalla de inicio:

Add below command in the file [File: start-screen.js]
     var text = game.add.text(0, 0, "Press Space to Start", textOptions);
     
### Trabajando juntos

En la ventana de Replit más abajo, empezamos el código con la línea `var text = game.add.text(0, 0, "Press Space to Start", textOptions);`.

![alt text](../img/startscreen.png "image to add the bird in the file")

En la consola verás `Press Space to Start` después de pulsar **run**:

![alt text](../img/startscreen_output.png "bird image in the output")
