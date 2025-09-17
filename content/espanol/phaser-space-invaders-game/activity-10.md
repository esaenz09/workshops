---
title: "Activity 10 - Adding a Title Screen"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 17
---

Ahora vamos a aprovechar la separación entre la escena 1 y la escena 2 añadiendo una pantalla de título para concluir nuestro juego.

¡Esto es muy sencillo! Primero comentaremos la línea `startGame()` que está al final de `create()` en la Escena 1. Vamos a usar la función `startGame()` para iniciar el juego en lugar de que comience automáticamente como antes:

<img src="../media/11/comment_out.png" alt="startGame comment out" style="width:950px;"/>

La consola volverá a un lienzo negro. Para crear una pantalla de título, necesitamos importar la imagen de fondo y algo de texto desde la sección `start page` de la escena 1:

<img src="../media/11/start_page.png" alt="start_page" style="width:950px;"/>

Solo puedes crear el fondo como una imagen en `create()`, ¡porque las imágenes solo pueden moverse en la función `update()`!

Para los textos, recomendamos usar diferentes `font` y `fills` para el texto del título y el texto de inicio.

Ahora llamaremos al método `startGame()` solo si el jugador hace clic para comenzar el juego:

<img src="../media/11/on_click.png" alt="on_click" style="width:950px;"/>

Your screen should look similar like this:
![title_screen](../media/11/title_screen.gif)

## ¡Felicidades!

¡Has completado todas las lecciones y creado tu propio juego Space Invader! ¡Diviértete con él! 👏🏽👏🏽👏🏽