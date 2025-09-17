---
title: "The Game's File Structure"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 2
---

Como puedes ver, ya hemos creado muchos archivos para ti. La estructura del juego ya está trazada, y tú irás llenando cada archivo con contenido. Así que, para empezar, primero debemos tener al menos una comprensión básica de qué hace cada archivo y cómo se relacionan entre sí.

En primer lugar, `phaser.min.js` es simplemente un archivo JavaScript que contiene código que permite que el juego ejecute Phaser, el framework que estamos usando para crear el juego. No tienes que preocuparte mucho por este archivo, y no lo editarás.

A continuación, mira `index.html`. Este es un archivo html que constituye la columna vertebral de todo nuestro proyecto al importar todos los archivos JavaScript que se utilizan.

Luego está `Game.js`. Este archivo representa esencialmente nuestro juego. Dentro de él, el código real del juego se ramifica a través de `Scene1.js` y `Scene2.js`. Estos archivos de escena son donde vas a escribir la mayor parte de tu código, y entraremos en más detalles sobre las escenas de Phaser un poco más adelante.

`PlayerBullet.js`, `EnemyBullet.js` y `Explosion.js` son archivos que crean objetos específicos para nuestro juego.

Finalmente, la carpeta `assets` contiene todas las imágenes que utiliza nuestro juego, para que sea más claro para los principiantes.