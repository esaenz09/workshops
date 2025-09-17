---
title: "Activity 4 - Adding Enemies"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 11
---

Ahora, ¡vamos a crear algunos enemigos para que nuestro jugador los combata! Primero carguemos una sprite sheet para nuestros enemigos en Scene 1 tal como lo hicimos para el jugador. Usa la misma sintaxis que usaste para cargar al jugador, pero usa un nombre diferente, `assets/enemies.png` como fuente de la sprite sheet, y un frameWidth y frameHeight de 16:

<img src="../media/5/load_sprite.png" alt="load_sprite" style="width:950px;"/>

Además, crea otra animación en Scene 1 de la misma manera en que creaste la animación del jugador (puedes usar los mismos argumentos para `frameRate` y `repeat`, pero recuerda usar `enemies` para `frames`):

<img src="../media/5/create_sprite.png" alt="create_sprite" style="width:950px;"/>

Este juego usará muchos enemigos que se ven idénticos y se comportan de forma muy similar. Para facilitar este código, usaremos un concepto en Phaser llamado group para controlar a todos nuestros enemigos a la vez. Un group es exactamente lo que parece: un grupo de cosas. Podemos referirnos a este group cuando queramos que se aplique un cambio a cada miembro del mismo.

Declaramos nuestro grupo de enemigos así:

```javascript
this.enemies = this.physics.add.group();
```

Esto creará un group llamado `enemies`.

Ahora, coloquemos nuestros enemigos en la pantalla. Para facilitar esto, usaremos otro método auxiliar llamado `createEnemies()` (que, nuevamente, ya ha sido creado para ti pero sin contenido):

<img src="../media/5/create_enemies.png" alt="create_enemies" style="width:950px;"/>

Ahora, llama a este método en el método `create()` en lugar de en `update()` como hicimos para el movimiento del jugador, porque solo queremos generar al enemigo una vez al inicio del juego:

<img src="../media/5/enemies_move.png" alt="enemies_move" style="width:950px;"/>

La sintaxis para crear una variable enemy en la coordenada (X, Y), con la sprite sheet `enemies`, y dentro del group `enemies` que declaraste anteriormente es la siguiente:

```javascript
var enemies = this.enemies.create(X, Y, 'enemies');
```

## Actividad 1: Colocar un enemigo

Pruébalo eligiendo una coordenada (X, Y) y colocando esta línea de código en el método createEnemies(). También necesitarás reproducir la animación justo después de crear el enemigo (así que estará en el método createEnemies()).
<img src="../media/5/enemy-one.PNG" alt="declare" style="width:950px;"/>
Debería verse algo así (con una ubicación potencialmente diferente: este enemigo se colocó en (300, 100))

## Actividad 2: Colocar más enemigos

Ahora añadamos más enemigos. Agrega un par de enemigos nuevos en el mismo método, pero ten cuidado porque cada variable de enemigo que crees dentro del mismo scope debe tener un nombre de variable diferente.
<img src="../media/5/enemy-multiple.PNG" alt="declare" style="width:950px;"/>

## Actividad 3: Colocar un bloque de enemigos

Ahora que ya le has tomado el truco, intentemos algo un poco más desafiante y crea los enemigos en este patrón de bloque mostrado abajo. Sin embargo, hay una condición: hazlo SIN declarar cada enemigo con una línea individual.

`PISTA: usa un for-loop anidado`
<img src="../media/5/enemy-block.PNG" alt="declare" style="width:950px;"/>