---
title: "Creating Animations"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 7
---

## Animación en Phaser

La animación funciona mostrando un conjunto de imágenes una tras otra muy rápidamente. Cuando hacemos esto rápidamente, nuestra mente lo percibe como movimiento. De alguna manera, estás engañando a la mente para que piense que este conjunto de imágenes es una sola cosa que se está moviendo.

![animation](../media/animation.png)

Usamos spritesheets para las cosas que queremos animar porque podemos crear esa animación recorriendo los spritesheets. Para animar spritesheets, hay dos pasos que debemos hacer.

El primer paso es crear las "instrucciones" para la animación

```javascript
this.anims.create({
    key: "dude_anim",
	frames: this.anims.generateFrameNumbers("dude"),
	frameRate: 10,
	repeat: -1
});
```

Esto crea una animación llamada "dude_anim" que funciona sobre "dude". El frame rate es esencialmente la velocidad de la animación. Repeat se refiere a cuántas veces se repite la animación cuando se reproduce, y un número negativo significa que la animación se reproduce infinitamente.

El siguiente paso es simplemente decirle al juego que reproduzca la animación especificada en nuestras instrucciones. Esto también se puede hacer en `create()`.

```javascript
this.dude.anims.play("dude_anim");
```

{{% notice note %}}

Cuando hagas esta instrucción play, la línea debe ir después de que el dude se haya colocado en la pantalla, porque el código se ejecuta de arriba hacia abajo; si hacemos esta instrucción play antes de colocar al dude, la computadora no sabrá qué animar.

{{% /notice %}}

Intenta animar al dude de la lección anterior. Siéntete libre de probar con los valores y ver cómo cambian el resultado final.
<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/PhasorAnimation" target="_blank">Abrir Replit</a>;