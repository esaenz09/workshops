---
title: "Methods"
date: 2022-08-06T13:24:17-07:00
draft: false
weight: 2
--- 

## Árboles binarios

Los árboles son un tipo especial de estructura de datos porque están compuestos por una colección de nodos conectados por aristas. No hay un inicializador único para crear un árbol genérico nuevo como en otras estructuras de datos que hemos visto. Para facilitar las cosas, nos centraremos específicamente en los **Árboles binarios**, que son un tipo de árbol con reglas estrictas sobre dónde debe ir cada nodo.

Las reglas para un árbol binario son:
* cada nodo tiene exactamente dos aristas, un nodo izquierdo y un nodo derecho
* los nodos a la izquierda son menores que el nodo actual
* los nodos a la derecha son mayores que el nodo actual

El árbol que vimos antes es un ejemplo de un árbol binario. ¡Echa un vistazo a cada uno de los nodos y comprueba por ti mismo que siguen las reglas!
![image](../img/tree.png)

## Buscar elementos

Antes de ver la implementación de cómo buscar con código, veamos cómo un árbol binario podría buscar un elemento. Cuando examinamos los elementos dentro de un árbol, siempre empezamos por el nodo raíz, que en un árbol binario debería estar, más o menos, en el medio de los datos.

Una vez que empezamos en la raíz, examinamos el valor y nos preguntamos "¿el valor que buscamos es menor, igual o mayor que este valor?" Si el valor es igual, ¡genial! Encontramos la respuesta. Si el valor que queremos es menor que el que tenemos actualmente, entonces vamos al nodo izquierdo y nos hacemos la misma pregunta. Si el valor que queremos es mayor que el que tenemos actualmente, entonces vamos al nodo derecho y nos hacemos la misma pregunta.

Fíjate si puedes seguir este ejemplo a continuación. Este es el mismo árbol que antes y queremos encontrar el valor 9.
![image](../img/binarysearch.gif)

## Recorrer elementos

Ahora que entendemos conceptualmente cómo buscar elementos, podemos ver que buscar elementos no es más que repetir la misma operación una y otra vez. Esto significa que si programamos la operación correctamente, todo el algoritmo de búsqueda está hecho.

Imagina que tenemos nodos que se definen así:
```js javascript
class Node {
    int value;
    Node left;
    Node right;
}
```

Ahora podemos aplicar la lógica para encontrar el elemento correcto que comentamos en la sección anterior. Considera este fragmento de código:
```js javascript
Node current = root;
if (current.value < desired) {
    current = root.right;
} else if (current.value > desired) {
    current = root.left;
}
```
Podemos ver que esto nos lleva de un paso al siguiente; luego podríamos usar esta lógica en un bucle `for` hasta encontrar el valor que buscamos.