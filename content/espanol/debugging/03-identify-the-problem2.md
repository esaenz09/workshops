---
title: "Step 1 - Finding the problem (Part 2)"
difficulty: "Intermediate"
weight: 4
draft: false
---

## Errores en tiempo de ejecución

Los errores del compilador son una cosa, pero los **errores en tiempo de ejecución y los bugs** son otra. Mientras que el compilador puede decirte fácilmente dónde mirar, los bugs en tiempo de ejecución son causados por cómo se ejecuta tu programa. Necesitamos entender qué está haciendo el programa cuando ocurre el bug:
- ¿Qué variables se están usando?
- ¿Qué instrucción se está ejecutando?
- ¿Falta alguna instrucción que necesitábamos?

En aplicaciones pequeñas, podemos usar **instrucciones de impresión** (print statements) en el código para descubrir rápidamente el estado de ejecución del programa. Las instrucciones de impresión son una forma rápida y rudimentaria de mirar dentro de un programa mientras se ejecuta, y con suerte podrás encontrar qué está causando el bug sin mucha dificultad.

## Búsqueda binaria

Uno de los algoritmos más sencillos que aprenderás o ya has aprendido es la **búsqueda binaria (binary search)**, que te permite buscar un elemento en una lista ordenada en tiempo logarítmico. La idea es comprobar el elemento medio de la lista ordenada y ver si coincide con el elemento que queremos; si encontramos el elemento, el algoritmo termina. Si el elemento es mayor, buscamos en la mitad superior de la lista. De lo contrario, buscamos en la mitad inferior de la lista. Repetimos el proceso hasta encontrar el elemento que buscamos.

|![Searching for number 7 in an ordered list of 10 numbers using Binary Search](../resources/binary_search.svg "A tree showing the search process of finding the number 7 in an ordered list of numbers 1 through 10 using Binary Search")|
|:--:|
|Searching for number **7** in an ordered list of **10** numbers using Binary Search|

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Samples-C" target="_blank">Abrir Replit</a>

Nuestro programa te pedirá que busques un nombre según la posición en la que se encuentra.

Abre la **Shell** en el programa de Replit y compila el programa:
``` bash
make BinarySearch
```

Ejecuta el programa así:
``` bash
./examples/BinarySearch
```

Deberías ver una lista de nombres y sus números en una lista. Busca a Emily escribiendo 6 en el aviso (prompt) y presiona `Enter`.

|![Searching for Amy](../resources/debugging_process_searching_for_amy.svg "A screenshot of a console that shows a list of names and their associated numbers. 'Number: 5, Name: Amy' is highlighted.")|
|:--:|
|Searching for Amy.|

Ahora ejecuta el programa otra vez y busca el número de `Ramona`. ¡El programa se rompe con el mensaje `Segmentation fault (core dumped)`! 😮

Ante un problema así deberías preguntarte: ¿cuál es el comportamiento del bug?
Los errores de segmentation fault suelen ser señal de uno de los siguientes problemas:
- Acceder a un arreglo fuera de sus límites.
- Desreferenciar un puntero NULL.
- Desbordamientos de memoria / pila.

Para más información, consulta una [Lista de razones comunes para Segmentation Faults en C](https://www.tutorialspoint.com/List-of-Common-Reasons-for-Segmentation-Faults-in-C-Cplusplus#:~:text=List%20of%20Common%20Reasons%20for%20Segmentation%20Faults%20in,7%20Stack%20overflow%208%20Writing%20to%20read-only%20memory).

Veamos el código que implementa la búsqueda binaria en nuestro programa:

1. La función `binary_search()` toma tres argumentos: el arreglo de elementos, la longitud del arreglo y el número que estamos buscando. Luego llama a la función recursiva `rbin_search()`.

2. `rbin_search()` realiza la búsqueda binaria de forma recursiva y devuelve el índice del elemento si lo encuentra. De lo contrario, devuelve `-1`.

Una `recursive function` divide un problema en muchos problemas más pequeños llamándose a sí misma y hace el problema más manejable con un conjunto de **casos base**. Una función recursiva que no termina normalmente tiene problemas en una de las siguientes áreas:

1. Los casos base están incompletos.
2. Las llamadas recursivas están establecidas de forma incorrecta.

¡Vamos a depurar!

## Usando instrucciones de impresión

Colocar instrucciones `print` a lo largo de tu código es una forma burda pero a veces efectiva de saber si tu código está funcionando como se espera. Ve y comprueba si `rbin_search()` está funcionando correctamente colocando instrucciones de impresión para ver cómo cambian los valores.

{{% expand "***Pista 1: ¿Qué hace que el problema que estamos tratando de resolver sea más pequeño?***" %}} 
- Intenta colocar la instrucción de impresión después de la variable `middle` en la función `rbinary_search` para ver cómo cambian los valores `lo`, `hi` y `middle`. Adelante, busca algo. 
|![Placing print statement to check values "lo", "hi" and "middle".](../resources/debugging_process_print_statement.svg "Screenshot of code that adds a print statement to line 17. The print statement prints out the values of 'lo', 'hi', and 'middle'.")|
|:--:|
|Placing print statement to check values `lo`, `hi` and `middle`.|

- Observa los valores a medida que se imprimen.
{{% /expand %}}

{{% expand "**Haz clic para ver la respuesta**" %}} 
La llamada recursiva para buscar en la mitad inferior del arreglo está buscando en la mitad superior por error.

Para arreglarlo, los argumentos `lo` y `hi` de `rbin_search()` deben ser `lo` y `middle-1`.

|![Fixing lower half recursive call.](../resources/debugging_process_fixing_lowerhalf_search.svg "Screenshot of code that highlights line 24 which reads 'return rbin_search(arr, lo, middle-1, element);'")|
|:--:|
|Fixing lower half recursive call.|

|![Looking how the "lo", "hi" and "middle" variables change when searching for Becky.](../resources/debugging_process_searching_for_becky.svg "Screenshot of the console that shows a list of people plus the debugging print statements that show how the values of 'lo', 'hi', and 'middle' change.")|
|:--:|
|Looking how the "lo", "hi" and "middle" variables change when searching for Becky.|

Ejecuta tu programa otra vez y busca un número menor que `5` y observa cómo cambian `lo`, `hi` y `index`.
{{% /expand %}}
<br/>

Las instrucciones de impresión no son la mejor herramienta cuando la complejidad del programa crece. Son extremadamente ineficientes y, si un programador olvida eliminarlas, otra persona (por ejemplo, un usuario que ejecute tu programa) podría ver esas impresiones. Usa las instrucciones de impresión solo en secciones aisladas de tu código y recuerda **SIEMPRE** eliminarlas 🙂.