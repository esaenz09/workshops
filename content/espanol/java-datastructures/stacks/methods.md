---
title: "Methods"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
--- 

## Pilas

Una pila es similar a una cola. La única diferencia son los nombres de los métodos y la manera en que recuperamos los elementos.

Antes de crear una pila, tendremos que usar `import` para traer la clase `Stack`. Para facilitar las cosas, podemos usar un `*` para importar todas las clases de la biblioteca. Se vería algo así.

```js javascript
// Esto importará la clase Stack, entre otras clases
import java.util.*;
```
Hay varios métodos que se pueden usar en una pila. Si te interesa, puedes buscar en Internet más información sobre estos métodos. Sin embargo, sólo vamos a explicar los métodos más importantes por ahora: `push()`, `peek()` y `pop()`.

<hr>

## Crear una pila
    
```js javascript
Stack driver = new Stack();
```

<hr>

## Agregar elementos

Para añadir un elemento a la pila, podemos usar el método `push()`. Esta operación `push()` coloca el elemento en la cima de la pila.

```js javascript
push(1);
push(2);
push(3);

// Crea una pila con elementos [3, 2, 1]
```

<hr>

## Acceder a elementos

Para obtener o recuperar el primer elemento de la pila, es decir, el elemento que se encuentra en la cima, podemos usar el método `peek()`. El elemento recuperado no se elimina de la pila.

```js javascript
stack.peek();

// Devuelve 3
// La pila contiene [3, 2, 1]
```

<hr>

## Eliminar elementos

Para eliminar un elemento de la pila, podemos usar el método `pop()`. El elemento se extrae (pop) y se elimina de la cima de la pila.

```js javascript
stack.pop();

// Devuelve 3
// La pila contiene [2, 1]
```

<hr>

Con estos tres métodos en mente, veamos un ejemplo.

```js javascript
import java.util.*;
public class Driver {
    public static void main(String []args) {
        // Inicialización por defecto de Stack 
        Stack stack = new Stack(); 
  
        // insertando los elementos 
        stack.push("Burger King"); 
        stack.push("Subway"); 
        stack.push("Telepizza"); 
  
        // Imprimiendo los elementos de la pila 
        System.out.println(stack); 
    }
}
```

Output:

```js javascript
["Telepizza", "Subway", "Burger King"]
```