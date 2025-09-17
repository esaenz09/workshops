---
title: "Phaser Fundamentals"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 3
---

## Parte 1: La variable Config

Repasemos algunos fundamentos de Phaser, un framework de juegos que usa HTML y JavaScript para crear juegos para la web. ¡Esto es lo que aprenderás a usar en este taller!

Ve a `game.js`. Todo juego con Phaser suele comenzar con una variable que almacena las configuraciones del juego (a menudo llamada config, como la que tenemos aquí).

```javascript
var config = {
  type: Phaser.AUTO,
  width: 512,
  height: 544,
  backgroundColor: 0x000000,
  scene: [Scene1, Scene2],

	physics: {
        default: 'arcade',
        arcade: {
            gravity: { y: 0 },
            debug: false
        }
    },
};
```

En esta variable verás que hemos definido una variedad de características del juego, como el ancho, la altura y el color de fondo. También hemos definido las escenas que vamos a usar (más información sobre escenas un poco más abajo). También puedes crear un juego sin escenas y simplemente poner todo el código en el archivo `game.js`.

También notarás que definimos la física del juego en Config. En el diseño de juegos, la física es uno de los aspectos más esenciales que definen la "sensación" de un juego. Por ejemplo, la física rebotadora de Mario lo hace distintivamente "sentir como Mario". Para nuestro juego, verás que usamos la física "arcade", un tipo de física en Phaser que es muy fácil de usar. Fíjate también en que en nuestra física definimos la gravedad en 0, porque nuestro juego es un Space Shooter y no necesitamos que la gravedad haga caer a los personajes.

Al final de `game.js`, puedes ver que pasamos la variable config a una variable game, algo que también es casi siempre necesario en un juego con Phaser.

## Parte 2: Escenas

Ahora, hablemos un poco sobre las escenas. Una escena es esencialmente un estado del juego en el que el usuario está interactuando. Se entiende mejor con un ejemplo:

Tomemos la famosa franquicia de juegos, Pokémon. Cuando juegas, a menudo estarás recorriendo el mundo. Cuando encuentras a un entrenador o a un Pokémon salvaje en la hierba alta, entras en una escena diferente para poder luchar. Después de terminar la batalla, puedes abrir el mapa para ver a dónde debes ir: esto también abre una escena distinta. Estas tres escenas funcionan completamente diferente y tienen sus propias mecánicas. Cuando cierras el mapa, el juego vuelve a la escena del mundo donde te mueves como jugador. Y cuando entras en batalla, cambias a la escena de batalla. Puedes ver cómo crear estos tres estados de juego sería completamente distinto: la batalla requiere un menú, el mundo requiere un espacio 2D y un jugador, y el mapa es esencialmente un gráfico interactivo. Separamos esto en escenas porque cada una debe crearse de forma totalmente diferente.

Puedes pensar en el usuario moviéndose entre escenas mientras juega. Sólo usa una escena a la vez, y cada una es casi como su propio mini-juego (aunque normalmente habrá una principal que no es exactamente "mini").

{{% notice info %}}

Técnicamente, podríamos usar una sola escena para estos tres estados de juego si quisiéramos (cómo dividir un juego en escenas depende del diseñador). Es físicamente posible hacerlo. Sin embargo, crear escenas separadas hará que la programación sea significativamente más fácil (en este caso, ni siquiera puedo imaginar cómo meterías todo en una sola sin simplemente superponer los visuales de una sobre otra).
{{% /notice %}}

Aquí hay otro ejemplo muy común de uso de escenas: una pantalla de título.

![Outliers game title screen](../media/title-game.png)

La primera escena muestra simplemente una pantalla de título que a menudo contiene cosas como ajustes, cargar una partida guardada y más. Una vez que el jugador hace clic en jugar, se cambia a una escena distinta, donde jugará el juego.

Esto es exactamente lo que vamos a hacer. La Scene 1 contendrá una pantalla de título, y la Scene 2 contendrá nuestro juego real. Por lo tanto, la Scene 2 tendrá la mayor parte del código, y será donde harás la mayor parte de tu trabajo.

## Parte 3: Lienzo infinito

Cuando inicias el juego en Replit, verás un lienzo en blanco en la pantalla donde eventualmente colocarás cosas. Sin embargo, solo estás viendo una parte del lienzo total: en realidad, el lienzo es infinito en todas las direcciones. El lienzo se comporta igual en todas las secciones: esto significa que los objetos pueden moverse y colocarse en partes del lienzo que el usuario no puede ver. Esto será importante porque, para nuestro juego, no queremos que las cosas salgan demasiado de la pantalla, por lo que necesitamos limitar nuestros objetos dentro de la pantalla o eliminarlos si salen.