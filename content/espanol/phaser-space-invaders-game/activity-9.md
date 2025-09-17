---
title: "Activity 9 - Adding Score, Levels, and Lives"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 16
---

Ahora añadiremos algunos números para cuantificar nuestro juego. Lo más fácil de implementar es el score. Crea una variable de texto en la esquina superior izquierda de la pantalla que muestre `Score: ` y el valor de una variable numérica que almacena el puntaje del jugador.

```javascript
this.scoreText = this.add.text(20, 10, "Score: " + this.score, {
    font: "25px Arial",
    fill: "white"
});
```

{{% notice hint %}}
Esta línea imprime la variable score en la esquina superior izquierda de la pantalla.

* `20` y `10` son los valores x e y
* `"Score: " + this.score` es el valor del texto
{{% /notice %}}

Puedes colocar esta línea en esta ubicación después de crear la variable score:

<img src="../media/10/create_score.png" alt="create_score" style="width:950px;"/>

Simplemente agrega una variable score y un texto en la pantalla que muestre "Score: 'variable score'". Actualizaremos la función `hitEnemy()` para que el jugador gane puntos en su score si derrota a un enemigo:

<img src="../media/10/hit_enemy_score.png" alt="hit_enemy_score" style="width:950px;"/>

Ahora añadiremos niveles. Los inicializaremos de la misma forma que hicimos con el score, pero esta vez lo imprimiremos en el centro de la pantalla en lugar de la esquina superior izquierda:

<img src="../media/10/create_level.png" alt="create_level" style="width:950px;"/>

Haremos los niveles bastante simples: cada vez que el jugador destruya a todos los enemigos, se alcanzará el siguiente nivel y se volverán a generar todos los enemigos. Para hacer que cada nivel sea más difícil que el anterior, haremos que los enemigos disparen con más frecuencia. Para que los enemigos disparen más a menudo, vamos a crear una variable `difficulty` y usarla cuando hagamos que los enemigos disparen aleatoriamente.

Con esta configuración, al cambiar la variable difficulty cambiamos la frecuencia con la que los enemigos disparan. Un valor de difficulty más bajo hará el juego más difícil porque aumenta la probabilidad de que un enemigo dispare.

Ahora, para que el nivel se actualice cuando el jugador destruya a todos los enemigos, crearemos un método `levelClear()` que actualizará la variable difficulty, reiniciará el timer de enemigos, creará nuevos enemigos (llamando a `createEnemies()`), y actualizará el texto del nivel en pantalla:

<img src="../media/10/level_clear.png" alt="level_clear" style="width:950px;"/>

Fíjate en que tenemos que crear un nuevo temporizador (timer) cada vez que creamos nuevos enemigos, de lo contrario los enemigos y el timer podrían no estar sincronizados. Además, recomendamos decrementar la variable difficulty menos cuando lleguemos a 200 porque la dificultad aumenta mucho más rápido a partir de ese punto.

No olvides actualizar `levelClear()` en `update()`:

<img src="../media/10/update_level_clear.png" alt="update_level_clear" style="width:950px;"/>

Ahora añadiremos vidas. De nuevo usaremos un método similar para inicializarla y colocarla en la esquina superior derecha de la pantalla:

<img src="../media/10/create_live.png" alt="create_live" style="width:950px;"/>

Para perder una vida cada vez que te golpean, añade este código en `hurtPlayer()`:

<img src="../media/10/hurt_player.png" alt="hurt_player" style="width:950px;"/>

Sin embargo, para que las vidas tengan sentido, hagamos que sea Game Over cuando el jugador se quede sin vidas. Empezaremos creando un texto que esté invisible en la pantalla dentro del método `create()`:

<img src="../media/10/create_game_over.png" alt="create_game_over" style="width:950px;"/>

Haremos que este texto sea visible cuando sea Game Over. Haremos esto en el método `hurtPlayer()`:

<img src="../media/10/hurt_player_restart.png" alt="hurt_player_restart" style="width:950px;"/>

Esto evita que el personaje reaparezca, muestra el texto de Game Over y reinicia el juego si el jugador hace clic en la pantalla.

Solo queda crear el método `restart()` al que se refiere este código:

<img src="../media/10/restart_function.png" alt="restart_function" style="width:950px;"/>

Esto restablece todo para comenzar el juego de nuevo

<img src="../media/10/game-play.gif" alt="gameplay"/>
