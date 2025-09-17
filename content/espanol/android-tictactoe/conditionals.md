---
title: "Conditionals"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 10
---
Podemos usar sentencias `if` para ejecutar una instrucción de código solo si se cumplen ciertas condiciones.

Por ejemplo:

```kotlin
if (isRainingOutside == true) {
    takeUmbrella = true;
} else {
    takeUmbrella = false;
}
```

Para nuestro juego, deberíamos usar sentencias `if` para determinar si un jugador tiene 3 coincidencias verticales, horizontales o diagonales.

Dentro de los paréntesis `()` junto a `if`, debes especificar una _expresión booleana_. Los **booleanos** son valores `true` o `false`. Podemos utilizar esto en nuestra instrucción `if`. Si la expresión es `true`, se ejecuta el código dentro de `{ }`. Si la expresión es `false`, se ejecuta el código dentro de `{ }` que sigue a la sentencia `else`.

También puedes conectar expresiones booleanas usando los operadores `&&` (AND) y `||` (OR).

Echa un vistazo a la función `CheckWinner()` en `MainActivity.kt` y piensa qué están haciendo todas las expresiones conectadas con `&&`.