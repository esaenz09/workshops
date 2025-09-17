---
title: "Methods"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
---

## Modificando elementos

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
        order.set(1, "Coke");
        // Esto reemplaza el primer elemento (Chicken Nugget) por "Coke"
    }
}
```
Usando `set()`, puedes establecer el elemento en la posición indicada por el índice a un nuevo elemento.

<hr>

## Eliminando elementos

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
        order.remove(2);
        // Elimina "Fries" del ArrayList
    }
}
```
De forma similar a `set()`, el método `remove()` elimina un elemento en la posición indicada por el índice.

<hr>

## Obtener el tamaño de un ArrayList

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
        System.out.println(order.size());
        // Imprime el tamaño del ArrayList, en este caso: 3
    }
}
```
`size()` devuelve el tamaño del `ArrayList`.

<hr>

## Iterando sobre elementos

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
        for (int i = 0; i < order.size(); i++) {
            System.out.println(order.get(i));
        }
        // Salida:
        // Whopper
        // Chicken Nugget
        // Fries
    }
}
```

Usando una combinación del bucle `for` y el método `get`, podemos recorrer el `ArrayList` e imprimir cada elemento en su índice.