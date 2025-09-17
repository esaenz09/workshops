---
title: "Introduction"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 1
---

Hemos aprendido sobre arrays e incluso nos hemos aventurado en arrays multidimensionales. Desafortunadamente, los arrays tienen muchas limitaciones y a veces pueden ser difíciles de usar. Una limitación de los arrays es su tamaño explícito. Si solo tienes espacio para 10 elementos en ese array, solo puedes almacenar hasta 10 elementos. `ArrayList`s son una gran estructura de datos que tiene un tamaño dinámico, es decir, que puedes añadir o quitar elementos en cualquier momento. Hay muchas más cosas que los `ArrayList` pueden hacer, lo que los convierte en estructuras de datos muy potentes.

![image](../img/arraylist.png)

Antes de crear un `ArrayList`, tendremos que importar la clase `ArrayList`. Se verá algo así.

```js javascript
import java.util.ArrayList; // importar la clase ArrayList
```

Recuerda, nuestro objetivo es crear un `ArrayList` que lleve el registro del pedido del cliente. Podemos hacerlo así:

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
    }
}
```

Como puedes ver, al igual que con los arrays, tenemos que declarar qué tipos de datos contendrá el `ArrayList`. En este caso, haremos que contenga `String`s, ya que los elementos del menú serán `String`s. 

Para añadir elementos a un pedido, usaremos el método `add()`. Si el cliente estuviera pidiendo en Burger King y quisiera pedir un combo con un Whopper, nuggets de pollo y patatas fritas, tu código podría verse así.

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
    }
}
```

Si quisiéramos obtener el primer elemento de un `ArrayList`, usaríamos el método `get()` junto con el número de índice del elemento, así:

```js javascript
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> order = new ArrayList<String>();
        order.add("Whopper");
        order.add("Chicken Nugget");
        order.add("Fries");
        System.out.println(order.get(0));
        // Imprime Whopper
  }
}
```

Hay muchos más métodos que puedes usar en un `ArrayList`, pero esto es solo la idea general de lo que puede hacer un `ArrayList`. Los métodos se pueden encontrar en la página siguiente.