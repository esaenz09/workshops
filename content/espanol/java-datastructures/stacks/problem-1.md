title: "Problem 1: Stack Basics"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
--- 

## Tarea 1: Revertir usando una pila

¡Oh no! ¡Contrataron a un nuevo becario y desordenó la lista de restaurantes! Las entradas de los restaurantes están en **orden inverso**. Por suerte, la pila es la estructura de datos perfecta para esto. ¿Puedes crear una nueva pila en el orden correcto?

{{% notice tip %}}
1. Recuerda que la pila es Último en entrar, primero en salir (LIFO; piensa en una pila de platos).
2. ¿Cómo se ve la pila original?
{{% /notice%}}

```js javascript
// Ejemplo de la pila actual
Stack<String> restaurants = new Stack<>();

restaurants.push("McDonalds");
restaurants.push("Carls Jr.");
restaurants.push("Burger King");
restaurants.push("Chipotle");
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/stackReverse" target="_blank">Launch Replit</a>

## Tarea 2: Mantener el historial

Otro uso práctico de la pila es la función de deshacer. Muchos programas hoy en día incluyen un botón de deshacer para llevar un registro de los cambios más recientes. ¡La pila es la estructura de datos perfecta para esto! ¿Puedes crear una función para deshacer el cambio reciente? Por ejemplo:

```js javascript
// Ejemplo de la pila actual
Stack<String> myOrder = new Stack<>();

restaurants.push("Drink");
restaurants.push("Fries");
restaurants.push("Pizza");
restaurants.push("Pizza");

// ¡El usuario pidió una pizza extra! ¿Cómo puedes deshacer el cambio reciente?

Stack.undo() // Eliminar el push más reciente
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/stackUndo" target="_blank">Launch Replit</a>