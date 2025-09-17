---
title: "Exercise 1 - Binary Tree Implementation"
difficulty: "Intermediate"
weight: 9
draft: false
---

El árbol binario es una de las estructuras de datos más simples en la informática y las ideas que emplea son muy útiles. Almacena datos ordenables y ofrece un tiempo de ejecución óptimo de O(log n) para buscar, agregar y eliminar elementos. Sin embargo, este rendimiento depende en gran medida del orden en que se agregan o eliminan los elementos, lo que limita su uso fuera del ámbito académico.

## La teoría

Un árbol binario consta de muchos nodos enlazados entre sí. Cada nodo tiene un nodo padre, o su predecesor, y hasta dos nodos hijos. Un nodo que no tiene hijos se llama hoja.

En un árbol binario con raíz (rooted), se especifica un nodo como raíz, lo que significa que no tiene padre. En el diagrama siguiente, el nodo A es el padre de los nodos B y C. Asimismo, B es el padre de D y E. A es la raíz, y D, E, F y G son hojas.

![Binary Tree Basics](../resources/e1-01.png "Binary Tree graph with labels pointing at the root, leaves, parent, and left and right children.") 

El árbol binario es una estructura de datos recursiva. Cada nodo puede contener de 0 a 2 hijos y 1 padre. Podemos limitarnos a mirar un subárbol específico del árbol original sin preocuparnos demasiado por todo el árbol en su conjunto; ese subárbol es, por sí mismo, un árbol binario válido.

### Uso del árbol binario

Podemos usar un árbol binario para almacenar información sobre el ordenamiento de una lista. Cada nodo puede almacenar un valor, y sus hijos deben ordenarse de la siguiente manera:
- El hijo izquierdo debe tener un valor menor que su padre.
- El hijo derecho debe tener un valor mayor que su padre.
- Los valores duplicados pueden almacenarse a la izquierda o a la derecha; sin embargo, es importante asegurarse de que los duplicados se almacenen de forma consistente. Si los duplicados se almacenan a la izquierda, solo se almacenarán a la izquierda, y lo mismo para la derecha.

El diagrama siguiente muestra un ejemplo de árbol binario. Observa que los hijos izquierdos son siempre menores que su padre, mientras que los hijos derechos son mayores. Además de esta propiedad de orden, no hay un requisito estricto sobre la forma del árbol.

![Binary Tree Example 1](../resources/e1-02.png "An example binary tree where the left children are all smaller than its parent, while the right children are larger.") 

### Añadir a un árbol binario

Para añadir un elemento, necesitamos encontrar dónde encaja en el árbol. Para ello, realizaremos un recorrido del árbol (tree traversal). La idea es movernos de nodo en nodo hasta encontrar un "hueco" para el elemento que queremos añadir. Primero, empezamos en la raíz. Comparamos el valor en la raíz con el elemento a añadir. Si el elemento es mayor, nos movemos al hijo derecho. En caso contrario, nos movemos al hijo izquierdo.

Podemos repetir este proceso hasta encontrar un nodo que pueda ser el padre del nuevo elemento. El diagrama siguiente ilustra cómo añadir 7 a un árbol binario.

![Binary Tree Add](../resources/e1-03.png "Diagram illustrating the process of adding 7 to a binary tree.")

1. En el paso 1 (azul), comparamos `10` y `7`. Como `7 < 10`, descendemos por el hijo izquierdo.
2. En el paso 2 (verde), comparamos `5` y `7`. `7 > 5`, así que descendemos por su hijo derecho, ¡solo para encontrar que `5` no tiene hijo derecho! Por tanto, podemos insertar `7` en ese lugar.

### Eliminar de un árbol binario

Eliminar un elemento es un poco más complicado. Primero necesitamos encontrar el elemento que vamos a eliminar. Sin embargo, una vez que lo eliminemos tendremos que rellenar el "hueco" que dejamos en el árbol. No podemos rellenar el hueco con cualquier elemento; necesitamos mantener la propiedad de orden del árbol binario. Un elemento conveniente para usar es el más profundo y más a la izquierda del subárbol derecho del hueco.

El diagrama siguiente muestra cómo eliminar elementos en varios casos. Las líneas punteadas indican que la conexión puede o no existir. Así que en el caso 2, por ejemplo, el padre azul podría no existir si el nodo a eliminar es la raíz del árbol.
- En el primer caso, el nodo no tiene hijos: podemos eliminarlo sin problemas.
- En el segundo caso, el nodo tiene 1 hijo (izquierdo o derecho). Podemos deslizar ese hijo hacia arriba para ocupar el lugar del nodo eliminado. Esto funciona tanto para el lado izquierdo como para el derecho.
- En el tercer caso, el nodo tiene 2 hijos. Hay varias formas de hacerlo, pero la que usaremos es tomar el elemento más pequeño del subárbol derecho e insertarlo en el "hueco" que dejamos. Si ese elemento tiene un hijo derecho (el nodo verde), necesitamos deslizar ese nodo hacia arriba, de modo que su antiguo padre (naranja) pase a ser el padre de ese hijo.

![Binary Tree Removal](../resources/e1-04.png "Diagram illustrating the 3 cases of removing an element from a binary tree.")

El tercer caso es complicado por la cantidad de casos límite que pueden aparecer. Por ejemplo, el valor mínimo del subárbol derecho podría ser el propio hijo derecho. O bien, el hijo mínimo podría no tener hijo derecho.

## La implementación

En el equipo de Nuevo hemos creado una implementación del árbol binario. Sin embargo, el programador fue descuidado y no revisó su trabajo, ¡así que hay errores y bugs! En este ejercicio, corregirás esos errores y bugs. Tu objetivo es que todas las pruebas pasen.

* Para depurar el código, puedes usar el comando `make debug`. Esto regenerará los archivos de depuración necesarios en el directorio `debug/` y ejecutará `gdb` por ti.
* Para usar `valgrind`, puedes ejecutar el comando `make valgrind`. Esto recompilará tu código y ejecutará `valgrind` con los argumentos apropiados.
* Para ejecutar las pruebas, puedes hacer clic en el botón verde "run", o usar el comando `make test`.

Echemos un vistazo a lo que hace el código existente. Primero, la estructura de datos del árbol binario se define en el archivo `binary_tree.h`. Puede referenciarse como un tipo llamado `BinaryTree`. Los datos se almacenan dentro de un tipo llamado `BTNode`, que representa un nodo del árbol binario.

El árbol en sí contiene un nodo centinela (sentinel), lo que facilita otras operaciones del árbol. Para obtener la raíz real del árbol, hay que referenciar el hijo izquierdo del centinela. Por tanto, el padre de la raíz es el nodo centinela, en lugar de `NULL`.

![Implementation Data Structures](../resources/e1-05.png "Picture of a BinaryTree structure that points out the sentinel node.")

{{% notice note %}}
Usar un centinela nos permite no preocuparnos por operaciones que implican actualizar el padre. Por ejemplo, si eliminamos un nodo, tendríamos que actualizar tanto el puntero del hijo en el padre como el puntero al padre en el hijo. Con un centinela, no nos preocuparíamos de que el puntero al padre sea `NULL`. Esto genera cierta confusión: ¡el nombre del centinela es `__root` en `BinaryTree`! Parece que el programador no prestó atención cuando lo escribió...
{{% /notice %}}

Cada nodo se asigna en el heap usando `malloc`, así que tendrás que asegurarte de que no haya fugas de memoria.

Las operaciones del árbol también se definen en `binary_tree.h`. Si no estás seguro de lo que hace una operación, asegúrate de leer su descripción allí. También incluiremos algunas imágenes de referencia abajo.

{{% notice tip %}}
Hay múltiples maneras correctas de implementar `treeRemove`. Nuestras pruebas no discriminarán entre diferentes maneras (correctas) de implementar el comportamiento. Siempre que se cumpla la propiedad del árbol binario, debería funcionar. La implementación que tenemos usa una operación `findMin`, que esencialmente busca el elemento más pequeño en el árbol binario. En otras palabras, el nodo más bajo y más a la izquierda del árbol.
{{% /notice %}}

Una vez más, la implementación no necesita manejar duplicados dentro del árbol. Además, no necesita implementar ninguna de las funciones `print` del árbol.

¡Buena suerte!

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Exercise-1" target="_blank">Launch Replit</a>

; mantenerlo claro para principiantes.
        Preservar términos técnicos, la sintaxis del código y el formateo. Traducir únicamente los comentarios que explican conceptos.
        Adaptar las referencias culturales cuando sea apropiado. No traduzcas el header key title; no traduzcas el image html.