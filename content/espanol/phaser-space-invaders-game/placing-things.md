---
title: "Placing things into Phaser"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 5
---

## Colocar texto

Ahora aprenderás cómo colocar cosas dentro de Phaser. Mira el repl a continuación.

¡Empecemos por cómo colocar texto!

```javascript
message = this.add.text(20, 10, "Hello World!", {
	font: "25px Arial",
	fill: "white"
});
```

Estas líneas de código crean una variable llamada "message". Esta variable añade el texto "Hello World" en la coordenada (X, Y) (20, 10) en la ventana de nuestro juego. El código también especifica que el texto será de color blanco, con la fuente Arial y tamaño de fuente 25 px.

Pon esta línea en tu método `create()` al final de la página y mira si aparece en la ventana de tu juego.

{{% notice note %}}

1. Al crear texto, el nombre de la variable no es el texto que se muestra en la pantalla; lo que se muestra es lo que pongas entre comillas.
2. Esta sintaxis también puede usarse para colocar texto que esté almacenado en una variable String.

{{% /notice %}}

{{% notice warning %}}

### ¡Ayuda! ¡La ventana de mi juego es muy pequeña!

No te preocupes, en realidad es relativamente grande, pero repl la minimiza por defecto. Puedes ampliar la vista de la ventana arrastrando las barras entre las secciones.

{{% /notice %}}

## Colocar un fondo

Los textos son muy simples, pero cuando queremos usar nuestros propios sprites para el juego (lo cual casi siempre harás), primero tienes que cargar el sprite en `preload()` antes de especificar su ubicación en `create()`.

Empecemos creando un fondo. Pon este código en tu método `preload()`.

```javascript
this.load.image('background', 'assets/sky.png');
```

Esto simplemente carga la imagen en el juego. A continuación, añadamos esta imagen al juego con `create()`:

```javascript
this.add.image(400, 300, 'sky');
```

Esta línea coloca la imagen en la coordenada (400, 300). Pruébalo y comprueba si tu fondo ya no es una pantalla negra.

{{% notice note %}}

La coordenada (400, 300) se refiere a la ubicación donde colocamos el píxel central de nuestra imagen. Esto significa que (400, 300) será el centro de la imagen. Colocamos la imagen aquí para que cubra toda la pantalla como debe hacerlo un fondo.

{{% /notice %}}

## Colocar un personaje

A continuación, pongamos un personaje en nuestro mundo.

El código que va en tu función preload() es así:

```javascript
this.load.spritesheet('dude', 'assets/dude.png', {
    frameWidth: 32,
    frameHeight: 48
});
```

Esto requiere un poco más de código porque es un spritesheet en lugar de un sprite simple. Los spritesheets se ven así:
![dude](../media/example-dude.png)
Este es el spritesheet para nuestro personaje. Los spritesheets son esencialmente una colección de sprites de un mismo personaje o elemento en varias posiciones. Cuando se reproducen uno tras otro, crean animación para nuestro juego (lo que describiremos con más detalle en la siguiente lección). Aunque para nosotros es obvio que son muchas imágenes del mismo personaje, el ordenador no lo detecta fácilmente por sí solo. Por eso necesitamos más sintaxis para decirle al ordenador qué tan grande es cada sprite dentro del spritesheet (en este caso, 32x48).

La sintaxis para colocar este spritesheet en `create()` es casi la misma que con la imagen, pero con una etiqueta de física:

```javascript
dude = this.physics.add.sprite(250, 200, 'dude');
```

En esta línea, estamos creando la variable "player" que añade la primera imagen del spritesheet en la coordenada (250, 200). La imagen también recibe el nombre "dude".

En esta línea, player es el nombre de una variable que estamos creando. 250 y 200 son las coordenadas X y Y donde hemos colocado el sprite, por lo que se colocará en la coordenada (250, 200) en nuestra pantalla. "dude" es el nombre de nuestro sprite, pero no intervendrá en esta lección en particular.

¡Intenta añadir el personaje! ¿Ves el personaje en tu pantalla?

{{% notice note %}}

1. Para ver el personaje, la variable dude en `create()` DEBE ser creada después del fondo. Esto se debe a que el código lo lee el ordenador de arriba hacia abajo, así que si el personaje se coloca antes que el fondo, el ordenador colocará el fondo encima del personaje, cubriéndolo y haciéndolo no visible para el usuario.
2. El dude se supone que está mirando a la izquierda porque al colocarlo por primera vez, los spritesheets siempre se colocan en la primera entrada de la hoja, y para nuestro dude, está mirando hacia la izquierda.

{{% /notice %}}

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/PhasorPlacingThings" target="_blank">Abrir Replit</a>