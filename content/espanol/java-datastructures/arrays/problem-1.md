---
title: "Problem 1: Array basics"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
---
<!--<link rel="stylesheet" href="../../style.css">-->

## Tarea 1: Imprimir

¡Hemos creado un array de restaurantes existentes en nuestro sistema! Necesitamos tu ayuda para imprimir todo para no incluir los mismos restaurantes.

{{% notice tip %}}
1. Usa un bucle `for` para imprimir el contenido del array.
2. Usa el método `length()` para encontrar el tamaño del array.
3. Mira el ejemplo abajo.
{{% /notice%}}

Si se nos da el siguiente array:

```js javascript
String[] restaurants = { "Burger King", "Chipotle", "Panda Express", "McDonalds" };
```

la respuesta debería imprimir:

```js javascript
String answer = "Burger King,Chipotle,Panda Express,McDonalds";
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Problem-1-getRestaurant" target="_blank">Abrir Replit</a>

## Tarea 2: Cambiar elementos

¡Oh no! ¡McDonalds se quedó sin comida! Cambia la lista de restaurantes antes de que las personas empiecen a ordenar en McDonalds y se queden decepcionadas sin comida. Por suerte, "Pizza Hut" está dispuesto a ayudar. Reemplaza McDonalds por Pizza Hut en el índice correspondiente.

{{% notice tip %}}
1. Lanzar
2. Encuentra primero el índice de McDonalds
3. Recuerda las comillas alrededor de `"Pizza Hut"`
4. Mira el ejemplo abajo!
{{% /notice%}}

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "McDonalds"};
// reemplazar "McDonalds" por "Pizza Hut"

```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Problem-2-insertRestaurant" target="_blank">Abrir Replit</a>