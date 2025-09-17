---
title: "Enabling User Inputs"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 9
---

## Entradas del usuario

Las entradas son esenciales porque sin que el usuario introduzca cosas mediante controles, nuestro juego no sería realmente un juego. Aunque Phaser admite una variedad de opciones de entrada, repasaremos tres que usarás en el juego Space Invaders.

## Teclas de flecha

Comencemos con uno de los controles más importantes: las teclas de flecha. Primero, crearemos una variable que pueda detectar cuando el jugador pulsa una tecla de flecha.

```javascript
this.cursors = this.input.keyboard.createCursorKeys();
```

Para usar esta variable, debes elegir entre cuatro expresiones booleanas.

```javascript
this.cursors.up.isDown
this.cursors.down.isDown
this.cursors.left.isDown
this.cursors.right.isDown
```

Cada una de estas expresiones booleanas será true si la tecla asociada está pulsada y false si no lo está.

## Barra espaciadora

Para añadir una entrada por la barra espaciadora, el proceso será muy similar al de las teclas de flecha. Primero crearemos una variable que detecte cuándo se pulsa la barra espaciadora.

```javascript
this.spacebar = this.input.keyboard.addKey(Phaser.Input.Keyboard.KeyCodes.SPACE);
```

Entonces podemos usar una expresión booleana para comprobar si se ha pulsado la entrada.

```javascript
Phaser.Input.Keyboard.JustDown(this.spacebar)
```

## Clic único

También puedes usar el mismo proceso que usamos para añadir entradas de teclas de flecha y barra espaciadora para los clics, pero veremos un método ligeramente diferente aquí porque es algo que probablemente usarás en el juego Space Invaders.

```javascript
this.input.once("pointerdown", this.restart, this);
```

Esta línea llama al método `this.restart` cuando el jugador hace clic. Sin embargo, esta es una entrada de un solo uso, lo que significa que, después de que el jugador haga clic una vez, ya no podrá utilizarse de nuevo sin volver a llamarla. Normalmente usarás esto en algún lugar dentro de update() o en las funciones auxiliares en lugar de en create().