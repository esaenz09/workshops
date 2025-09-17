---
title: "Comments"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 6
---
Los desarrolladores a menudo necesitan colaborar con otros desarrolladores. Los comentarios son una forma sencilla para que los desarrolladores escriban notas en el código y se comuniquen con otros. Los comentarios son ignorados por la computadora; por lo tanto, también son una manera fácil de indicarle a la computadora que no ejecute ciertas líneas de código. Hay dos formas de crear comentarios:

1. Para comentar una sola línea, coloca `//` al principio de una línea de código. Por ejemplo:

```kotlin
// Este es un comentario de una sola línea.
```

2. Para comentar varias líneas a la vez, indica el inicio del comentario con `/*` y el final con `*/`. Por ejemplo:

```kotlin
/* Esto es un comentario de varias líneas.
Esta línea también forma parte del comentario. */
```

Para eliminar un comentario (o descomentar una línea), simplemente borra `//` en un comentario de una sola línea, o los caracteres `/*` y `*/` en un comentario de varias líneas.

{{% notice tip %}}
## Trabajando juntos

1. Escribe `//` delante de `Toast.makeText(this, "Welcome to Tic-Tac-Toe”, Toast.LENGTH_LONG).show()`. Después de pulsar el botón de reproducción (►), comprueba que `Welcome to Tic-Tac-Toe` no aparezca en la pantalla.
2. Borra los `//` y, en su lugar, rodea `Toast.makeText(this, "Welcome to Tic-Tac-Toe”, Toast.LENGTH_LONG).show()` con `/*` y `*/`. Comprueba que `Welcome to Tic-Tac-Toe` sigue sin imprimirse en la consola después de pulsar el botón de reproducción (►).
3. Borra tanto `/*` como `*/`, y pulsa el botón de reproducción (►). Welcome to Tic-Tac-Toe debería imprimirse ahora en la consola.
   A lo largo de los rompecabezas de hoy, verás varios comentarios de varias líneas y comentarios `// PUZZLE` (como el del Rompecabezas 2). Estos comentarios nos guiarán para completar el juego Tic-Tac-Toe, así que asegúrate de comprender cómo comentar y descomentar código.

{{% /notice %}}