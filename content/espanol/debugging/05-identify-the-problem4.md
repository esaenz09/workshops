---
title: "Step 1 - Finding the problem (Part 4)"
difficulty: "Intermediate"
weight: 6
draft: false
---

## Otro tipo de error: errores de memoria

La pesadilla de C/C++, los errores de memoria son uno de los tipos de fallos más frustrantes que existen. No resolverlos puede dar lugar a comportamiento indefinido (¡fallos no reproducibles!) y fugas de memoria. Por tanto, arreglarlos es una prioridad importante.

{{% notice note %}}

Una fuga de memoria ocurre cuando tu programa asigna memoria usando malloc o calloc (u otras llamadas de asignación de memoria) y no la libera. La memoria queda "perdida": no hay una forma (fácil) de recuperarla hasta que el programa termine.

{{% /notice %}}

Afortunadamente, también existen programas que te ayudan a encontrar errores de memoria, y uno de estos programas es `valgrind`. Valgrind es una herramienta que no solo busca errores de memoria, sino que te muestra exactamente dónde ocurren en tu código.
Usemos valgrind para encontrar dónde ocurren los errores de memoria. Como ejemplo, tenemos una implementación rudimentaria de un vector en C, que es la versión de la librería estándar de C++ para un arreglo de tamaño dinámico.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Samples-C" target="_blank">Abrir Replit</a>

Primero crea el programa usando 

```bash 
make Vector
``` 

Ahora ejecútalo con

```bash
examples/Vector
```

Fíjate en que hay un error llamado "double free" (doble liberación). Este es un tipo de error de memoria causado por llamar a `free` sobre un puntero dos veces.

Ahora, en lugar de usar gdb, usa valgrind para comprobar cómo se asigna y usa la memoria. Ejecuta el comando:

```bash
valgrind --tool=memcheck --leak-check=full examples/Vector
```

Debería quedar claro que valgrind detectó algunos errores, quizá relacionados con el double free (observa que el `ERROR SUMMARY` al final muestra varios errores detectados).

Echemos un vistazo a algunos de los errores.

![Valgrind error 1](../resources/w4-02.png "Screenshot of console error with the text 'Invalid read of size 8 at 0x484522D...'")

El error mostrado arriba se llama lectura inválida (invalid read), que suele darse porque estás leyendo memoria que fue liberada en otro bloque. Valgrind te permite ver dónde se liberó y se asignó la memoria:

![Valgrind error 2](../resources/w4-03.png "Screenshot of console error with the text 'Address 0x4b74040 is 0 bytes inside a block of size 16 free'd...'")

El bloque de memoria fue asignado por la función `malloc` en `createVectorInt`, que fue llamada desde la función `main`. El bloque fue liberado con `free` por la función `pushBack`.

Finalmente, en el resumen del heap puedes ver que hubo 96 bytes que quedaron "perdidos": en otras palabras, hubo una fuga de memoria. Esto ocurrió porque olvidamos llamar a `deleteVectorInt` sobre el vector al final de la función main.

![Valgrind error 3](../resources/w4-04.png "Screenshot of console error with the text 'HEAP SUMMARY: in use at exit: 96 bytes in 2 blocks... 96 bytes in 2 blocks are definitely lost in loss record...'")

Valgrind proporciona una gran cantidad de información que puedes usar para cazar errores de memoria en tus programas en C y C++. No solo te informa dónde están ocurriendo los errores, sino también dónde se asignaron los bloques de memoria y dónde se liberaron posteriormente (o no se liberaron, en el caso de una fuga de memoria). ¿Puedes encontrar el bug que causa todas las lecturas inválidas en el ejemplo del vector?

{{% expand "**Haz clic para mostrar la respuesta**"%}}
Fíjate en que cuando estamos realojando (realloc) el arreglo, olvidamos actualizar `list->__arr`! Esto significa que escribimos en un puntero que ya fue liberado, lo que explica las lecturas y escrituras inválidas que vemos en Valgrind, las dobles liberaciones (porque llamamos a free sobre ese puntero ya liberado) y las fugas de memoria (ya que nunca volvemos a referirnos a los arreglos recién asignados). Todo lo que hay que hacer es asignar ese puntero al nuevo arreglo actualizado, lo que debería corregir el error.
{{% /expand %}}
<br/>

En los ejercicios se te pedirá que corrijas cualquier error de memoria que aparezca.