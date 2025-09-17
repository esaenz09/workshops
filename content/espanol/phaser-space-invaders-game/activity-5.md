---
title: "Activity 5 - Making the Enemies Move"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 12
---

Por el momento, los enemigos son un poco aburridos porque simplemente están quietos. ¡Hagámoslos moverse un poco! Nuestro objetivo será hacer que se desplacen de izquierda a derecha así:
![move](../media/6/enemy-move.gif)

Empecemos haciendo que los enemigos se muevan hacia la izquierda justo después de ser creados. Podemos lograrlo simplemente añadiendo una línea de código:

```javascript
enemy.body.velocity.x = -90;
```

Coloca en nuestro método createEnemies():

<img src="../media/6/move_enemies.png" alt="move enemies" style="width:950px;"/>

Pero si pruebas el código ahora, verás que los enemigos siguen yendo hacia la izquierda indefinidamente debido al lienzo infinito de Phaser. Hagamos que cambien de dirección antes de salir de la pantalla. Podemos hacer esto con un temporizador, una herramienta que nos permite llamar a una función después de un cierto periodo de tiempo. La función que llama el temporizador cambiará la dirección del enemigo. También podemos hacer que el temporizador se ejecute indefinidamente para que siga llamando a la función después de cada intervalo de tiempo (que es lo que haremos aquí). Coloca el siguiente temporizador al final del método `createEnemy()`.

```javascript
this.enemyTimer = this.time.addEvent({
    delay: 1500,
    callback: this.changeEnemyDirection,
    callbackScope: this,
    loop: true
});
```

<img src="../media/6/timer_function.png" alt="timer_function" style="width:950px;"/>

Este es un temporizador que llama continuamente al método `changeEnemyDirection()` después de un determinado intervalo de tiempo. Sin embargo, aún no hemos puesto ningún contenido en dicho método. Hagámoslo ahora: añade código en el método `changeEnemyDirection()` que cambie la dirección de cada enemigo en el grupo enemies (¡ésta es una de las razones por las que creamos un grupo!):

<img src="../media/6/change_direction.png" alt="change_direction" style="width:950px;"/>

{{% notice hint %}}

Fíjate, sin embargo, en que (si usaste los mismos valores de temporizador que nosotros), tu nave se está moviendo dentro y fuera de la pantalla. En lugar de fijar la posición a la pantalla como hicimos con la nave del jugador, simplemente moveremos un poco la posición inicial del enemigo hacia la derecha (porque el temporizador tiene el tiempo adecuado para ir de un lado a otro de la pantalla).

{{% /notice %}}