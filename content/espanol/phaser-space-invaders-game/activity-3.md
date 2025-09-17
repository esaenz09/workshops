---
title: "Activity 3 - Add Keyboard Input to Move the Player"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 10
---

Ahora, vamos a permitir que nuestra nave se mueva cuando el jugador use el teclado. El primer paso es crear un atributo cursor en el método `create()` de `Scene2.js`:

<!--- ![create_cursor_key](../media/4/create_cursor_key.png) --->
<img src="../media/4/create_cursor_key.png" alt="create_cursor_key" style="width:950px;"/>

La forma más eficiente de crear el movimiento es crear una función auxiliar que use el atributo cursor para comprobar si se ha pulsado una tecla. Ya hemos creado esta función para ti, y se llama `movePlayer()`:

<!--- ![move_player_function](../media/4/move_player_function.png) --->
<img src="../media/4/move_player_function.png" alt="move_player_function" style="width:950px;"/>

Luego movemos al jugador con esta función. Podemos llamar a esta función en el método `update()` para comprobar el movimiento en cada ciclo de actualización (esto ya también se ha hecho por ti).

Ahora, ve al método `movePlayer()` y escribe código que compruebe el movimiento y mueva al jugador en consecuencia.

{{% notice hint %}}

* Recomendamos una velocidad de movimiento de 200
* Usa una sentencia if
* Después de que hayas hecho las sentencias `if`, puede que notes que tu jugador sigue moviéndose incluso después de dejar de pulsar las teclas. Para arreglar esto, piensa: cuando el jugador no está pulsando el teclado, ¿qué debería hacer la nave?

{{% /notice %}}

¡Ahora pruébalo! Sin embargo, puede que observes una cosa: el jugador puede moverse fuera de la pantalla así:

<!--- ![bounds](../media/4/player-off.gif) --->
<img src="../media/4/player-off.gif" alt="bounds" style="width:100px;"/>

Esto ocurre porque Phaser usa un lienzo (canvas) ilimitado que existe incluso fuera de la ventana de la pantalla. Podemos arreglarlo restringiendo al jugador dentro de la pantalla con una línea de código:

```javascript
this.player.body.setCollideWorldBounds(true); // el jugador no puede salirse de la pantalla
```

Encuentra el `create()` método de la Escena 2:

<!--- ![set_bound](../media/4/set_bound.png) --->
<img src="../media/4/set_bound.png" alt="set_bound" style="width:950px;"/>

Ahora, que tu jugador está limitado dentro de la pantalla, deberías poder mover tu nave así:

<!--- ![animation spaceship and background](../media/4/player-move-example.gif)
 --->
<img src="../media/4/player-move-example.gif" alt="animation spaceship and background" style="width:300px;"/>