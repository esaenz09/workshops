---
title: "Booleans"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 9
---

Los booleanos son afirmaciones que pueden ser verdaderas o falsas. A diferencia de las cadenas o los números, los booleanos almacenan enunciados de verdad: ¿lo que digo es verdadero o falso? Por ejemplo, si pregunto, "¿Eres un robot?", esta pregunta produce un resultado verdadero o falso, que llamamos un booleano. En este caso, como no eres un robot (¡esperemos!), produciríamos `false`. También podemos usar operadores matemáticos para crear expresiones booleanas. Aquí hay algunos ejemplos; sin embargo, fíjate en los símbolos inusuales para "igual a" y "no igual a":

| Operador | Descripción           | Operador | Descripción                     |
| -------- | --------------------- | -------- | ------------------------------- |
| `<`      | Menor que             | `>`      | Mayor que                       |
| `<=`     | Menor o igual que     | `>=`     | Mayor o igual que               |
| `==`     | Igual a               | `!=`     | No igual a                      |

Como de costumbre, usa `System.out.println` para imprimir tus resultados:

```kotlin
System.out.println(10 < 8);
System.out.println((3 * 6) == (32 - 14));
```
{{% notice tip %}}
## Trabajando juntos

Borra todo tu texto de `System.out.println` en tu código. Intenta adivinar las respuestas de las siguientes expresiones. Usa `System.out.println` para comprobar tus respuestas.

- 54 < (10 + 32)
- (37 / 5) == 7
- "Hello" + "World" == "Hello World"
- false == false
{{% /notice %}}

## Operadores booleanos

También puedes conectar expresiones booleanas usando el operador `&&` (AND) y el operador `||` (OR). Por ejemplo, supongamos que pregunto: "¿Eres humano, y Nuvi es un robot?" La palabra "y" conecta las dos preguntas verdadero-falso. En este caso, si es verdadero que eres humano, y también es verdadero que Nuvi es un robot, entonces el resultado general es `true`. Aquí tienes una tabla que describe qué ocurre cuando conectamos booleanos:

| Expresión                        | Resultado | Expresión                              | Resultado |
| -------------------------------- | --------- | -------------------------------------- | --------- |
| <code>true && true</code>        | `true`    | <code>true &#124;&#124; true</code>    | `true`    |
| <code>true && false</code>       | `false`   | <code>true &#124;&#124; false</code>   | `true`    |
| <code>false && true</code>       | `false`   | <code>false &#124;&#124; true</code>   | `true`    |
| <code>false && false</code>      | `false`   | <code>false &#124;&#124; false</code>  | `false`   |

Para resumir, `&&` requiere que ambas expresiones booleanas sean verdaderas, mientras que `||` solo requiere que una de las dos expresiones booleanas sea verdadera. Aquí tienes algunos ejemplos más:

- `(5 < 8) && (9 != 10)` produce `true` ya que tanto 5 es menor que 8 como 9 no es igual a 10.
- `(6 != 2 * 3) || (8 < 2 * 4)` produce `false` porque ambas expresiones `(6 != 2 * 3)` y `(8 < 2 * 4)` son `false`.