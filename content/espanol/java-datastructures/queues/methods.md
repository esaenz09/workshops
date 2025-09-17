---
title: "Methods"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
--- 
## Colas de prioridad

Una `PriorityQueue` se utiliza cuando los objetos deben procesarse en función de su prioridad. En este caso, queremos ordenar la cola por el tiempo que el cliente ha estado esperando. Se sabe que una Queue sigue el algoritmo First-In-First-Out (primero en entrar, primero en salir), pero a veces los elementos de la cola necesitan procesarse según la prioridad; es entonces cuando entra en juego la `PriorityQueue`. La PriorityQueue se basa en un heap de prioridad. Los elementos de la cola de prioridad se ordenan según el orden natural o mediante un Comparator proporcionado al construir la cola, dependiendo del constructor que se utilice.  

Antes de crear una cola, tendremos que `import`ar la clase `PriorityQueue`. Para facilitar las cosas, podemos usar un `*` para importar todas las clases de la biblioteca. Se vería algo así.

```js javascript
// Importará PriorityQueue, entre otras clases
import java.util.*; 
```
Hay varios métodos para usar en una Priority Queue y, si te interesa, siéntete libre de buscarlos en Google. Sin embargo, ahora solo vamos a hablar de los métodos más importantes: `add()`, `peek()` y `poll()`.

<hr>

## Creando una cola de prioridad
    
```js javascript
Queue<Integer> orders = new PriorityQueue<>();
```

Hay varias maneras de ordenar la cola de prioridad y depende de ti decidir cómo quieres implementarla.

<hr>

## Agregar elementos

Puedes agregar a una cola usando el método `add()`. La `PriorityQueue` ordenará automáticamente los elementos por ti. Su comportamiento predeterminado es según el orden natural de los objetos, pero puedes cambiarlo según lo que necesites.

```js javascript
add(1);
add(2);
add(3);

// Crea una cola con elementos [1, 2, 3]
```

<hr>

## Acceder a elementos

`peek()` devolverá el elemento superior sin eliminarlo.

```js javascript
queue.peek();

// Devuelve 1
// La cola contiene [1, 2, 3]
```

<hr>

## Eliminar elementos

`poll()` devolverá el elemento superior y lo eliminará de la cola.

```js javascript
queue.poll();

// Devuelve 1
// La cola contiene [2, 3]
```

<hr>

Con estos tres métodos en mente, echemos un vistazo a un ejemplo.

```js javascript
import java.util.*;
 
class PriorityQueueDemo {
   
      // Método principal
    public static void main(String args[]) {
        // Creación de una cola de prioridad vacía
        PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>();
 
        // Añadiendo elementos a pQueue usando add()
        pQueue.add(60);
        pQueue.add(30);
        pQueue.add(10);
 
        // Imprimiendo el elemento superior de la PriorityQueue
        System.out.println(pQueue.peek());
 
        // Imprimiendo el elemento superior y eliminándolo
        // del contenedor PriorityQueue
        System.out.println(pQueue.poll());
 
        // Imprimiendo el elemento superior nuevamente
        System.out.println(pQueue.peek());
    }
}
```

Entonces tenemos tres clientes con tiempos de espera distintos de `10`, `30` y `60`. ¿Qué crees que imprimirá el compilador?

Vamos a intentar entender un poco el código. En la primera línea, llamamos a `pQueue.peek()`. ¿Qué hace `peek()`? Peek simplemente devuelve el elemento en la parte superior. ¿Qué hay en la parte superior? Dado que ya está ordenada, debería imprimir el elemento más pequeño, que es `10`.

¿Y `pQueue.poll()`? Hará lo mismo que peek en este caso, pero ahora elimina el elemento superior de la cola, que es `10`.

¿Qué pasa si volvemos a llamar a `peek()`? Como `10` ya no existe, ahora será `30`.

Así que la salida final podría verse así:

```js javascript
10
10
30
```

¿Un momento? ¿No queríamos que las personas que más tiempo han esperado estuvieran primero en la cola? Parece que la cola devuelve primero los elementos más pequeños, pero lo que realmente queremos es el elemento más grande. Para conseguir esto, solo tendríamos que instanciar la cola de forma un poco diferente. `Collections.reverseOrder()` esencialmente invierte el orden de nuestra cola. ¡Así!

```js javascript
PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>(Collections.reverseOrder());
```
Ahora nuestra implementación debería estar lista.

```js javascript
import java.util.*;
 
class PriorityQueueDemo {
   
      // Método principal
    public static void main(String args[]) {
        // Creación de una cola de prioridad vacía
        PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>(Collections.reverseOrder());
 
        // Añadiendo elementos a pQueue usando add()
        pQueue.add(60);
        pQueue.add(30);
        pQueue.add(10);
 
        // Imprimiendo el elemento superior de la PriorityQueue
        System.out.println(pQueue.peek());
 
        // Imprimiendo el elemento superior y eliminándolo
        // del contenedor PriorityQueue
        System.out.println(pQueue.poll());
 
        // Imprimiendo el elemento superior nuevamente
        System.out.println(pQueue.peek());
    }
}
```

Pregunta de verificación: ¿Qué mostrará ahora este `pQueue`?

Answer:
```js javascript
60
60
30
```