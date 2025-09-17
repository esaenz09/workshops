---
title: "Problem 1: Queue Basics"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
--- 
<!--<link rel="stylesheet" href="../../style.css">-->

## Tarea 1: Vaciar la Cola para Nuevos Pedidos

¡Se ha añadido un nuevo restaurante a Nuevo Eats! ¡Han llegado muchos pedidos y la Queue está llena de órdenes! La popularidad de los distintos tacos creció rápidamente y el restaurante está sobrecargado. ¡Busca una forma de eliminar todos los elementos para salvar el restaurante!

{{% notice tip %}}
1. ¿Cómo puedes iterar a través de la Queue?
2. ¡Intenta vaciar la Queue mientras la recorres!
3. ¡Mira el ejemplo del menú!
{{% /notice %}}

```js javascript
// Esto usa una lista como organizador de la cola.
Queue<String> orders = new PriorityQueue<>();

orders.add("Fish Taco");
orders.add("Beef Taco");
orders.add("Chicken Taco");
orders.add("Fish Taco");
orders.add("Beef Taco");
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Clear" target="_blank">Launch Replit</a>

## Tarea 2: Usar Priority Queue para encontrar el precio mínimo

Un restaurante está usando una Priority Queue para gestionar pedidos. El restaurante quiere poder ver los pedidos en función de sus precios para preparar mejor los platos que están haciendo. Específicamente, les gustaría poder encontrar el enésimo precio mínimo que hay actualmente en su lista. Escribe una función que examine su cola de pedidos y devuelva el enésimo precio mínimo.

{{% notice tip %}}
1. ¿Cómo vas a asegurarte de que la lista esté ordenada?
2. ¿Qué hace más fácil encontrar el precio mínimo?
3. ¿Y si buscan el quinto precio mínimo (o más bajo)?
{{% /notice %}}

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Min" target="_blank">Launch Replit</a>