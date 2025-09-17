---
title: "Activity 8 - Allowing the Enemies to Shoot"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 15
---

Ahora haremos que los enemigos devuelvan el fuego al jugador. Cada enemigo disparará de forma aleatoria, y la `difficulty` (que más tarde se incrementará con cada nivel) se define por la frecuencia con la que disparan aleatoriamente.

El rayo del enemigo es bastante similar al rayo del jugador. De nuevo crearemos un archivo `enemyBeam.js` muy parecido al `playerBeam.js`, con casi el mismo código pero con nombres de variables y números diferentes:

<img src="../media/9/enemy_bullet.png" alt="enemy_bullet" style="width:950px;"/>

Compartiremos el sprite y la animación para los rayos del jugador y los del enemigo. Sin embargo, durante la implementación crearás un grupo separado para los proyectiles enemigos:

<img src="../media/9/enemy_projectiles.png" alt="enemy_projectiles" style="width:950px;"/>

También necesitamos crear una dificultad para este juego (explicaremos más sobre `difficulty` más adelante, pero por ahora `difficulty` hará que el enemigo dispare):

<img src="../media/9/add_diff.png" alt="add_diff" style="width:950px;"/>

{{% notice hint %}}
* Recomendamos establecer `difficulty` en 1000.
* Si estableces `difficulty` en 1000, el número aleatorio se escogerá entre 1 y 1000. Solo si el número aleatorio es 1, el enemigo disparará.
* El enemigo disparará continuamente si pones `difficulty` a 1.
{{% /notice %}}

Para hacer que los enemigos disparen aleatoriamente, primero crearemos un método `enemyShoot()`:

<img src="../media/9/enemyShoot.png" alt="enemyShoot" style="width:950px;"/>

y lo llamaremos en el método `update()`:

<img src="../media/9/update_player_shoot.png" alt="update_player_shoot" style="width:950px;"/>

eso crea un nuevo proyectil enemigo a una tasa aleatoria especificada.

Luego, necesitamos actualizar los proyectiles enemigos. Debemos asegurarnos de que cada rayo se elimine cuando corresponda.

Tendrás que actualizar los rayos enemigos en `enemyBeam.js` como lo hiciste en `playerBeam.js`:

<img src="../media/9/update.png" alt="update_player_shoot again" style="width:950px;"/>

También necesitas actualizar cada proyectil enemigo en Scene 2, de manera similar a cómo actualizamos los proyectiles:

<img src="../media/9/update_enemy_projectiles.png" alt="update_enemy_projectiles" style="width:950px;"/>

Al final, el juego debería verse algo así:
<img src="../media/9/enemy-shoot.gif" alt="enemyShoot" style="width:950px;"/>