---
title: "Setting up the Enemies"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 7
---

Ahora que Nuvi está listo para moverse, ¡hagamos que reciba a unos alienígenas en el universo! Localiza el archivo png del alien llamado "alien_pink" en la carpeta Drawings. Luego, arrastra y suelta el alien_pink en la hierarchy. Reescala el enemigo para que coincida con el tamaño de Nuvi, ya que es demasiado grande.

<img src="../img/6_nuvi_and_enemy.png" alt="Enemy is scaled to match Nuvi's size" width="400"/>

Ahora, si ejecutáramos el juego, Nuvi corre sobre el alien rosa. Queremos que Nuvi colisione con él. Para hacerlo, añade un BoxCollider2D al alien como lo hicimos con Nuvi y redimensiónalo si es necesario. Ahora, si volvemos a ejecutar el juego, Nuvi choca contra el alien en lugar de pasar por encima.