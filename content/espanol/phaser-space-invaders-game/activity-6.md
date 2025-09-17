---
title: "Activity 6 - Restarting the Player after Being Destroyed"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 13
---

Hemos creado enemigos bastante decentes, pero ahora hay algo mal: ¡en realidad no te hacen nada! Específicamente, no pueden dañarte de ninguna forma. Cambiemos eso. En el juego final, habrá dos maneras de recibir daño: que un enemigo dispare un láser y que lo toques directamente. Empecemos por lo segundo, ya que es un poco más sencillo.

La colisión es relativamente fácil en Phaser.

Empecemos por importar una hoja de sprites de explosión e implementar su animación en la Escena 1:

<img src="../media/7/load_sprite.png" alt="load_sprite" style="width:950px;"/>

<img src="../media/7/create_sprite.png" alt="create_sprite" style="width:950px;"/>

¡Esta será una explosión que se reproducirá cuando el jugador sea destruido!

Phaser tiene formas muy convenientes para manejar colisiones entre objetos. Simplemente podemos añadir la siguiente línea al método create() en la Escena 2:

```javascript
this.physics.add.overlap(this.player, this.enemies, this.hurtPlayer, null, this);
```

<img src="../media/7/overlap_hurtPlayer.png" alt="overlap with player" style="width:950px;"/>

Esta línea hace que se llame al método hurtPlayer() cuando `this.player` y un miembro del grupo `this.enemies` se superponen. Llamará a hurtPlayer con `this.player` y `this.enemies` como argumentos.

Esta línea hará que el método hurtPlayer() sea llamado cuando el jugador y un objeto del grupo de enemigos se toquen, pasando las variables player y enemy al método como argumentos. Ahora vamos a crear el método hurtPlayer():

<img src="../media/7/function.png" alt="hurtPlayer" style="width:950px;"/>

Primero destruiremos el enemigo y deshabilitaremos al jugador para el `paso 4 y 5` con estas líneas:

```javascript
enemy.destroy();
player.disableBody(true, true);
```

Esto hace que tanto el enemigo como el jugador desaparezcan (el enemigo ha sido eliminado, pero el jugador solo está invisible y no interactivo). Ahora hagamos que el jugador reviva después de una breve pausa (la pausa permite al jugador algo de tiempo para reaccionar al daño). Para esta pausa, usaremos otro temporizador (como hicimos para cambiar la dirección del enemigo) en el `paso 7`. La sintaxis será la misma, pero llamaremos a la función resetPlayer(), usaremos un tiempo de espera más corto y tampoco haremos que el temporizador se repita.

Una vez que hayas creado el temporizador, trabajemos en el método `resetPlayer()`:

<img src="../media/7/resetPlayer.png" alt="reset_player" style="width:950px;"/>

Primero, elige unas coordenadas de reaparición y cambia el valor (X, Y) del jugador a esa ubicación (todavía podemos cambiar la posición de la nave así porque todavía existe, solo está deshabilitada). Luego, habilita al jugador con esta línea:

```javascript
this.player.enableBody(true, x, y, true, true);
```

Una vez que hayas implementado esto, la colisión debería verse así:
<img src="../media/7/respawn-first.gif" alt="collision" style="width:950px;"/>

A continuación, vamos a crear un nuevo objeto de explosión editando `explosion.js`:

<img src="../media/7/explosion.png" alt="explosion" style="width:950px;"/>

Fíjate en que extiende Phaser.GameObjects.Sprite. Esto nos permitirá usar el constructor de esta clase mediante herencia. El parámetro de nuestro objeto Projectile es simplemente la escena y dos números (x e y) — más adelante verás que pasamos la propia Escena 2. Podemos usar esta escena para acceder a todo lo que contiene. Todo lo que hará este archivo es crear un objeto que reproducirá la animación de explosión en la ubicación especificada. Todo el código que esta clase necesita está contenido en el constructor, y solo hay 2 líneas de código que necesitas completar.

Ahora, ve al método `hurtPlayer()` en `scene2.js`:

<img src="../media/7/create_explosion.png" alt="create_explosion" style="width:950px;"/>

Aviso:
Crearás dos objetos de explosión:

- Uno con la escena y las coordenadas del jugador como parámetros,
- El otro con la escena y las coordenadas del enemigo como parámetros.

A continuación, observa cómo la reaparición del jugador es un poco brusca. Haremos que esta transición sea más suave con un tween después de generar al jugador:

<img src="../media/7/reset_tween.png" alt="reset_tween" style="width:950px;"/>

Un tween es, básicamente, una herramienta que te permite animar una característica u opción de un objeto. Por ejemplo, en este caso estamos animando la alpha (es decir, la visibilidad) del jugador. Comenzaremos estableciendo la alpha del jugador en 0.5 y luego usaremos el tween para animarla hasta la visibilidad completa y normal.

```javascript
var tween = this.tweens.add({
    targets: this.player,
    y: config.height - 64,
    ease: 'Power1',
    duration: 1500,
    repeat: 0,
    onComplete: function(){
        this.player.alpha = 1;
    },
    callbackScope: this
});
```

¡Ahora por fin hemos terminado! ¡La animación de revivir del jugador se ve mucho mejor!

<img src="../media/respawn-second.gif" alt="collision" style="width:950px;"/>