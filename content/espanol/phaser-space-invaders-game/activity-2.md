---
title: "Activity 2 - Animating the Player's Ship"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 8
---

Para darle vida a nuestro juego, ¡pongamos las cosas en movimiento! Anima la nave del jugador que hemos creado.

<!--- ![animation_part](../media/4/animation_part.png) --->
<img src="../media/4/animation_part.png" alt="animation_part" style="width:950px;"/>

<!--- ![play_animation](../media/4/play_animation.png) --->
<img src="../media/4/play_animation.png" alt="play_animation" style="width:950px;"/>

Una vez que tu nave esté animada, debería verse así. ¡Fíjate en las llamas saliendo del motor de la nave! (Aunque puede ir más rápido o más lento según la tasa de frames que elegiste).

<!--- ![animation](../media/4/animation-ship.gif) --->
<img src="../media/4/animation-ship.gif" alt="animation" style="width:300px;"/>

Daremos un toque final a la animación: también moveremos el fondo. Cambia el fondo de una imagen normal a un TileSprite así:

```javascript
this.background = this.add.tileSprite(0, 0, config.width, config.height, "background");
this.background.setOrigin(0, 0);
```

Los TileSprites permitirán que nuestro fondo se mueva aunque no sea un spritesheet, porque son un tipo de Sprite con textura repetida, por lo que pueden desplazarse a través del Canvas infinito de Phaser.

<!--- ![move_background](../media/4/move_background.png) --->
<img src="../media/4/move_background.png" alt="move_background" style="width:950px;"/>

¡Pruébalo ahora! Si funciona correctamente, ¡parecerá que la nave está volando por el espacio!

<!--- ![animation spaceship and background](../media/4/animation-flying.gif) --->
<img src="../media/4/animation-flying.gif" alt="animation spaceship and background" style="width:300px;"/>
; manteniéndolo claro para principiantes. Conserva términos técnicos, la sintaxis del código y el formato. Traduce solo los comentarios que expliquen conceptos. Adapta las referencias culturales de forma apropiada. No traduzcas la clave de encabezado title; no traduzcas el HTML de las imágenes