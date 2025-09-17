---
title: "Exercise 3 - The Burrows-Wheeler Transform"
difficulty: "Intermediate"
weight: 11
draft: false
---

La transformada de Burrows-Wheeler (BWT) es un algoritmo usado en compresión de datos. Toma como entrada una cadena y devuelve una cadena codificada, que normalmente agrupa caracteres similares juntos.

## La teoría

El algoritmo es relativamente directo y fácil de entender.

1. Toma la cadena de entrada y extrae todas sus transformaciones rotacionales. (Ver imagen).
2. Ordena las rotaciones en orden lexicográfico ascendente.
3. Toma la última columna de la transformada ordenada; esa es la salida.

![Burrows-Wheeler Transform](../resources/e3-01.png "The 3 steps of a Burrows Wheeler Transform")

En el diagrama anterior usamos la cadena `banana` como ejemplo. El `\0` es un símbolo usado para denotar el final de la cadena (como el carácter terminador nulo en C), pero es lexicográficamente el CARÁCTER MÁS GRANDE cuando se compara con los demás.

Una manera eficiente de implementar la BWT es usando una estructura de datos llamada suffix array. Para crear un suffix array, primero tomamos todos los sufijos de una cadena de entrada y les damos una etiqueta numérica. Luego ordenamos los sufijos lexicográficamente.

![Suffix Arrays](../resources/e3-02.png "Steps of creating a suffix array")

Usando `Nuevo\0` como ejemplo, primero tomamos sus sufijos y los listamos. Luego los ordenamos en orden lexicográfico, con `\0` siendo el carácter terminador nulo como antes y actuando como el carácter más grande. Finalmente, tomamos el índice de la primera letra de cada sufijo y lo ponemos en un arreglo. Por ejemplo, el índice de la letra `N` en `Nuevo\0` es `0`, mientras que el índice de `e` es `2`. Como son alfabéticamente los más pequeños, van en las posiciones 0 y 1 del arreglo, respectivamente.

Podemos pensar en los sufijos como rotaciones para la transformada de Burrows-Wheeler. Todo lo que tenemos que hacer es añadir el prefijo que "recortamos" al final de la cadena. Así, `evo\0` se convierte en `evo\0Nu` cuando queremos pensar en el sufijo como una rotación. Entonces, si hacemos esto para todos los sufijos, obtenemos las rotaciones ordenadas que queremos para la transformada de Burrows-Wheeler.

![Suffixes to Rotations](../resources/e3-03.png "Table of sorting rotations from suffixes for the Burrows-Wheeler transform")

Un punto clave es que en realidad no necesitamos almacenar las rotaciones porque el índice en el suffix array ya nos da esa información. Si `suffix_array[i] == 0`, entonces sabemos que la rotación que estamos viendo es `Nuevo\0`. Si `suffix_array[i] == 3`, entonces la rotación que estamos viendo es `vo\0Nue`. Puedes pensar en ello como rotar `N` posiciones a la derecha en el caso `suffix_array[i] == N`. La ilustración anterior demuestra esto.

Así que, dicho esto, podemos obtener el último carácter de la rotación simplemente tomando `suffix_array[i]` y restándole 1, luego tomando el módulo del tamaño total de la cadena para obtener el índice de la cadena original que estamos buscando. Esto nos da la transformada de Burrows-Wheeler para cualquier cadena dada.

## La implementación

La estrategia de implementación que usamos es la que destacamos arriba: construir un suffix array, luego tomar los índices, restarles 1 y después realizar una operación de módulo con la longitud de la cadena (incluyendo el terminador nulo).

Hemos implementado el suffix array y con él la transformada de Burrows-Wheeler. Sin embargo, estábamos cansados en ese momento y se nos escaparon bastantes errores. Este ejercicio puede ser complicado porque implica mucho manejo de índices y descubrir cómo podemos ser ingeniosos usándolos. Como pista para corregir los errores, la mayoría de los bugs están centrados en el suffix array y en cómo lo usamos.

{{% notice tip %}}
El carácter terminador nulo puede estropear cómo imprimes tus cadenas. En este ejercicio, tienes que imprimir la cadena transformada carácter por carácter, porque el terminador nulo hará que la función `printf` deje de imprimir cuando lo encuentre. El siguiente código imprimirá el resultado de llamar a `bwt(dest, src)`, donde `STR_LEN` es la longitud estática de la cadena **incluyendo el terminador nulo**.
```c
for(int i = 0; i < STR_LEN; ++i) {
    printf("%c", dest[i]);
}
```
Ten en cuenta que `strlen()` devuelve la longitud de la cadena, sin el terminador nulo.

Una última pista: `%` en C **no** es el operador de módulo en sentido matemático; es el operador de resto. Quizá por eso algunos indexados han salido mal...
{{% /notice %}}

Todas las funciones están documentadas en `bwt.h`. Usa cualquier herramienta como gdb y valgrind a tu favor. ¡Buena suerte!

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Exercise-3" target="_blank">Abrir Replit</a>