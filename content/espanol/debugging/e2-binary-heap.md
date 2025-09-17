---
title: "Exercise 2 - Binary Heap Implementation"
difficulty: "Intermediate"
weight: 10
draft: false
---

Un binary heap es una estructura de datos importante que se usa más a menudo para implementar un tipo de dato llamado priority queue. También se usa conceptualmente en el algoritmo de ordenamiento llamado heapsort. Su característica distintiva es la consulta en `O(1)` para el valor más grande o más pequeño dentro de su contenido, dependiendo del tipo de heap del que estemos hablando.

## La teoría

El binary heap es, conceptualmente, un árbol binario completo. Esto significa que los nodos se añaden al árbol en orden por niveles, y la profundidad del árbol solo aumenta cuando no hay espacio en el nivel más profundo del árbol.

Además de esta restricción estructural, se sigue la propiedad de orden del heap: los hijos de un nodo deben tener un valor mayor o menor que el propio nodo. En un **min-heap**, los hijos deben ser mayores. En un **max-heap**, los hijos deben ser menores. Efectivamente, esto significa que la raíz debe contener el elemento más grande en el heap.

El siguiente es un ejemplo de un max binary heap, que es el tipo de heap en el que nos centraremos en este ejercicio.

![Binary Heap Example](../resources/e2-01.png "Max binary heap example")

Puedes ver que cada nodo tiene 2 o ningún hijo, excepto el nodo más a la derecha. Los nodos se llenan de izquierda a derecha antes de empezar una nueva fila. Todos los hijos son más pequeños que su padre.

{{% notice note %}}
Los duplicados se manejan fácilmente en este esquema. Necesitamos mantener que todos los hijos sean en realidad menores *o iguales* que su padre.
{{% /notice %}}

Podemos usar un arreglo para representar esta estructura de datos. Un nodo i se puede acceder por su índice, i. Para acceder a su hijo izquierdo, multiplicar por 2. Para acceder a su hijo derecho, multiplicar por 2 y sumar 1. El diagrama siguiente lo ilustra:

![Binary Heap Array](../resources/e2-02.png "Image of a binary heap and its corresponding array")

### Añadir a un binary heap

Para añadir un elemento, primero lo insertamos en el siguiente hueco disponible. Después, corregimos retroactivamente cualquier problema causado por esto deslizando el elemento hacia arriba y permutando nodos hasta que alcance una posición estable, es decir, hasta que su padre sea mayor o igual que él.

El diagrama abajo ilustra este proceso al agregar `34` al binary heap de ejemplo.
1. Insertamos `34` en la última casilla de forma tentativa (círculo verde, paso 1).
2. Luego comparamos con su padre (flecha azul), y encontramos que `34 > 19`. Por tanto, intercambiamos los dos nodos.
3. En el paso 2 comparamos con `85`, y encontramos que `34 < 85`, lo que indica que hemos terminado.

![Binary Heap Add](../resources/e2-03.png "Illustrating the process of adding to a binary heap")

### Eliminar el Max del Heap

Un max binary heap también necesita soportar `removeMax`, que elimina el elemento más grande del heap. Por suerte, el elemento más grande está simplemente en la raíz; sin embargo, necesitamos arreglar los problemas causados por el hueco que dejamos.

Para rellenar ese hueco, tomamos el último elemento y lo colocamos en la posición superior. Como antes, corregimos retroactivamente cualquier problema que esto cause. Repetimos swaps hacia abajo con el hijo mayor hasta que alcance una posición estable en el heap.

El diagrama abajo muestra cómo ocurre una eliminación en un max heap.
1. La raíz se elimina y se sustituye por el elemento más a la derecha en la fila inferior.
2. En el paso 1 comparamos `19` y `42`. Puesto que `42` es el mayor de los 2, comparamos `12` y `42` (flecha azul), y vemos que `12 < 42`. Por tanto, intercambiamos `12` con `42`.
3. Repetimos el proceso para el paso 2. Encontramos que `28` es el mayor de los 2 hijos, y como `12 < 28` volvemos a intercambiar.
4. Finalmente alcanzamos una posición estable para el paso 3.

![Binary Heap Removal](../resources/e2-04.png "Illustrating the process of removing the max from a binary heap")

## La implementación

En nuestra implementación, empezamos la indexación desde `1` para ahorrar un poco de computación. Así que la raíz del binary heap está ubicada en `heap.__arr[1]` en lugar de `heap.__arr[0]`. Todas las funciones tienen comentarios sobre su funcionamiento en `binary_heap.h`.

La implementación **será** probada contra duplicados, así que asegúrate de manejarlos. Además, aunque el heap tiene tamaño fijo, los datos se almacenan en el heap. ¡Asegúrate de liberar (`free`) la memoria de los datos!

{{% notice tip %}}
Las funciones `createHeap` y `heapPrint` ya han sido probadas y se ha verificado que funcionan.
{{% /notice %}}

Tu objetivo es ejecutar `make test` y no obtener errores. Usa cualquier herramienta, como `gdb`, `valgrind`, etc., a tu favor. ¡Buena suerte!

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Exercise-2" target="_blank">Abrir Replit</a>; manténlo claro para principiantes.
Preserva los términos técnicos, la sintaxis de código y el formato. Traduce solamente los comentarios que expliquen conceptos.
Adapta las referencias culturales según corresponda. No traduzcas la clave de título del encabezado; no traduzcas el html de las imágenes.