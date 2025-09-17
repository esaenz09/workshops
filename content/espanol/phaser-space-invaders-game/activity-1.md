---
title: "Activity 1 - Place Background and Player Ship"
date: 2020-08-20T11:45:38-07:00
draft: false
weight: 6
---

Esta actividad tendrá dos partes: cargar el fondo del juego y cargar la nave que el jugador controlará más adelante (por ahora será solo una imagen que no se moverá). Para ambas actividades, el método será muy similar: primero subiremos la imagen al juego en Scene 1 y luego la haremos visible en Scene 2. Puedes pensar en Scene 1 como usada para subir la imagen al juego y en Scene 2 para crear los elementos que hayamos subido.

## Parte 1: El fondo

Empecemos por el fondo. De nuevo, para añadir imágenes al juego, primero las subiremos en Scene 1 y luego las colocaremos en nuestro juego en Scene 2. Primero ve al Paso 1 en la función `preload()` en `Scene1.js`:

<img src="../media/3/step1.png" alt="background part 1" style="width:950px;"/>

Ahora, carga la imagen de fondo en `preload()`.

Para repasar,
* No ocurrirá nada después de completar esta línea porque solo estás cargando la imagen para uso futuro, no colocándola en ningún sitio.

* `imageID` es el nombre que le das a la imagen.

* `imagePosition` es la ubicación de la imagen.
(si una imagen se llama example.png y está en la carpeta assets, `imagePosition` será assets/example.png)

A continuación, ve a Paso 1 y Paso 2 en la función `create()` en `Scene2.js`. Cada paso requerirá una línea de código, creando 2 líneas en total:

<img src="../media/3/background_section.png" alt="background_section" style="width:950px;"/>

Carga la página y comprueba si el fondo funciona. La consola a tu derecha debería verse así:

<img src="../media/3/after_add_image.png" alt="background_after_add_image" style="width:950px;"/>

## Parte 2: La nave del jugador

Haremos algo casi igual con el jugador pero con una sintaxis diferente porque la nave del jugador es un spritesheet en lugar de una imagen normal (verás por qué en la siguiente actividad).

Para esta parte harás el Paso 2 en la función `preload()` en `Scene1.js`:

<img src="../media/3/step2.png" alt="background player ship step2" style="width:950px;"/>

* `SpriteID` y `SpritePosition` funcionan igual que `imageID` e `imagePosition`.

* `FrameWidth` será 32 y `FrameHeight` será 48.

y la sección `player` en `Scene2.js`:

<img src="../media/3/player_section.png" alt="background player_section" style="width:950px;"/>

{{% notice hint %}}

Si la sección del jugador está completada correctamente, pero el jugador no aparece en pantalla, intenta cambiar `x` e `y`; ¡puede estar fuera de la pantalla!

{{% /notice %}}

Después de añadir la nave del jugador, tu consola debería verse así:

<img src="../media/3/after_add_player.png" alt="background after_add_player" style="width:950px;"/>