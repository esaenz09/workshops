---
title: "Preload, Create, and Update"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 4
---

## Los métodos Preload, Create y Update

Ahora veamos nuestras escenas, que eventualmente contendrán el código de nuestro juego. Si te desplazas por ellas, verás que cada escena tiene un constructor (porque es una clase) y también tres métodos grandes: `preload()`, `create()`, `update()`. También hay varias funciones auxiliares en la Escena 2, pero hablaremos de los tres métodos mencionados porque son fundamentales para entender Phaser.

Con la forma en que hemos configurado las escenas, `preload()` y `create()` están en la Escena 1 y `create()` y `update()` están en la Escena 2. Estas tres funciones son las herramientas principales que cualquier juego que use Phaser empleará.

## Preload()

Comencemos describiendo `preload()` — esta función esencialmente carga cosas en nuestro juego. Pueden ser imágenes, variables y prácticamente cualquier otra cosa que quieras definir para que el juego la use. Las cosas cargadas en el juego con `preload()` NO se usan ni se colocan en ninguna parte del juego hasta que las uses más adelante. Puedes pensar en este método como un espacio de almacenamiento que se llena una vez antes de que empiece el juego. La mayoría de los elementos deben colocarse en `preload()` antes de ser usados en cualquier parte del juego.

## Create()

A continuación está `create()`. Esta función también es relativamente sencilla: se ejecuta una vez al inicio del juego y permite al usuario colocar las cosas que ha precargado con `preload()` y crear objetos dentro de nuestro juego, como animaciones, detectores de colisión, texto, grupos y mucho más.

## Update()

Finalmente, la última función es `update()`. Mientras que `preload()` y `create()` se ejecutan solo una vez al inicio del juego, `update()` se ejecuta constantemente.

{{% notice info %}}
Mientras juegas, es posible que hayas encontrado el término "FPS". Esto se refiere a los "fotogramas por segundo" del juego, o a la frecuencia con la que se actualiza un nuevo fotograma en la pantalla. Un fotograma es, esencialmente, una llamada única al método `update()`. Phaser normalmente funciona a 60 FPS, lo que significa que el método `update()` se llama 60 veces en un solo segundo.
{{% /notice %}}

El método `update()` se usa de diversas maneras. Una es para el movimiento: si asignamos a un objeto que se mueva un poco dentro de `update()`, entonces cuando juguemos, parecerá que el objeto se mueve de forma fluida porque `update()` se está llamando con tanta frecuencia que no podemos ver las pausas entre cada movimiento. También podemos usar `update()` para comprobar constantemente si se ha dado una entrada. Por ejemplo, si queremos que el jugador pueda disparar cuando se presione la barra espaciadora, podemos usar una sentencia if que compruebe la barra espaciadora dentro de la función `update()`, de modo que el juego esté revisando constantemente esto.