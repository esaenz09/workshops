---
title: "Activity 7 - Allowing the Player to Shoot"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 14
---

Ahora queremos añadir una de las partes más importantes del juego: ¡disparar a los enemigos! Aunque podemos derrotar a los enemigos estrellándonos contra ellos, eso no será buena idea una vez que añadamos vidas más adelante. Crearemos un efecto de disparo creando un objeto para el haz (beam) usando un archivo JavaScript separado (como hicimos con la explosión).

Comenzaremos con cosas básicas: cargar una spritesheet y una animación en Scene 1 para los beams del jugador:

<img src="../media/8/scene1_preload.png" alt="scene1_preload" style="width:950px;"/>

La ubicación de la spritesheet es `assets/beam.png` y el ancho y alto de cada fotograma es 32:

<img src="../media/8/scene1_create.png" alt="scene1_create" style="width:950px;"/>

Ahora en Scene 2 haremos algo similar a lo que hicimos con los enemigos y crearemos un grupo para los beams de modo que podamos manipularlos fácilmente. Crea un grupo y nómbralo "projectiles":

<img src="../media/8/projectiles_step1.png" alt="projectiles" style="width:950px;"/>

Ahora ve a `playerBeam.js`：

<img src="../media/8/constructor_xy.png" alt="constructor_xy" style="width:950px;"/>

Fíjate que, al igual que `Explosion.js`, extiende Phaser.GameObjects.Sprite y usa la palabra clave `super()` en su constructor. Completa el código en el constructor. Esto requerirá que reproduzcas la animación del beam, habilites el body y establezcas la velocidad en Y (y-velocity) del beam a la velocidad a la que quieras que viaje.

Ahora que tenemos lo básico del beam, permitamos que el jugador dispare cuando pulse la barra espaciadora. De forma similar a cómo creamos una variable para procesar las teclas del puntero para el movimiento del jugador, crearemos otra variable para procesar cuando el jugador pulse la barra espaciadora:

<img src="../media/8/control_space.png" alt="control_space" style="width:950px;"/>

Ahora crearemos un método playerShoot():

<img src="../media/8/player_shoot.png" alt="player_shoot" style="width:950px;"/>

y lo llamaremos en el método update() como hicimos con movePlayer():

<img src="../media/8/update_player_shoot.png" alt="update_player_shoot" style="width:950px;"/>

El método playerShoot comprobará si la barra espaciadora ha sido pulsada y disparará un beam si es así. "Disparar un beam", en este caso, significa crear un objeto playerBeam y añadirlo al grupo projectiles si el jugador está activo (todavía vivo).

¡Pruébalo ahora! Sin embargo, hay dos grandes problemas: el beam no daña al enemigo en absoluto y el beam también sigue yendo para siempre debido al canvas infinito de Phaser.
<img src="../media/8/blast-first.gif" alt="blast" style="width:950px;"/>

Arreglemos primero ese segundo problema. Aunque este problema no afecta directamente la jugabilidad, podría ser un problema porque si el beam sigue existiendo fuera de la pantalla, entonces el ordenador tiene que gastar tiempo gestionándolo. Si hay demasiados beams que el ordenador tiene que atender, ¡podría causar lag! Lo que haremos es utilizar una función update en playerBeam.js que destruya el beam si sale de la pantalla.

La única manera de hacer que estas funciones update funcionen, sin embargo, es llamarlas en la función update de nuestra Scene 2 así:

```javascript
for(var i = 0; i < this.projectiles.getChildren().length; i++) {
    var beam = this.projectiles.getChildren()[i];
    beam.update();
}
```

Puedes insertarlo en esta ubicación:

<img src="../media/8/update_projectiles.png" alt="update_projectiles" style="width:950px;"/>

Ahora, para probar esto, podemos simplemente cambiar el valor de altura (height) al que el beam se autodestruye por uno que esté en la pantalla:

<img src="../media/8/player_bullet_update.png" alt="player_bullet_update" style="width:950px;"/>

El código funciona correctamente si el beam desaparece en la altura específica. Después de comprobar que el código funciona, podemos cambiar este valor por uno que esté por encima de la pantalla.

<img src="../media/8/blast-disappear.gif" alt="blast" style="width:950px;"/>

Puedes ver en este gif que el beam desaparece una vez que alcanza una altura especificada (usamos 50). De nuevo, tras confirmar que funciona, podemos cambiar el número 50 por otro que esté un poco fuera de la pantalla (por ejemplo 10) y sabremos que el código probablemente sigue funcionando igual.

Ahora, ¡hagamos que el enemigo sea destruido si es alcanzado por un beam! En realidad podemos hacer esto con una detección de overlap similar a la que usamos para comprobar si el jugador está tocando al enemigo:

<img src="../media/8/projectiles_step2.png" alt="overlap projectiles" style="width:950px;"/>

Crea una línea de código que use la misma sintaxis que la línea que usamos para detectar si el jugador y el enemigo han colisionado, pero esta vez comprueba si el enemigo y el beam han colisionado.

Sin embargo, no podemos usar el método hurtPlayer() porque el jugador no está siendo herido y no queremos que el jugador reaparezca cuando el enemigo es golpeado. Crearemos una nueva función llamada `hitEnemy()`:

<img src="../media/8/hit_enemy.png" alt="hit_enemy" style="width:950px;"/>

Añade código a `hitEnemy()` para que cree una explosión en la ubicación del enemigo y elimine el beam y el enemigo.

Al final, ¡disparar debería verse así!
<img src="../media/8/blast-final.gif" alt="blast" style="width:950px;"/>