---
title: "Problem 1: HashMap Basics"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
--- 

## Tarea 1: Uso de HashMap para organizar datos

¡Es una fiesta! Un cliente organiza una gran fiesta de cumpleaños para más de 20 personas. Cada persona tiene su propio pedido. Para mantener organizado el pedido masivo, decides crear un HashMap de `String`s. La cumpleañera se llama Isabella, pero su nombre se perdió en la lista. ¿Puedes averiguar qué pidió Isabella?

{{% notice tip %}}
1. ¿Recuerdas los métodos de HashMap?
2. ¡Mira el ejemplo de pedido abajo!
{{% /notice%}}

```js javascript
// Ejemplo del HashMap actual
HashMap<String, String> order = new HashMap<String, String>();

// clave, valor
order.put("Justin", "Sprite");
order.put("George", "Coke");
order.put("Sam", "Fanta");
order.put("Eva", "Coke");
order.put("Olivia", "Coke");
...
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/HashMapGet" target="_blank">Launch Replit</a>; manteniéndolo claro para principiantes. 
Preserva los términos técnicos, la sintaxis del código y el formato. Solo traduce los comentarios que expliquen conceptos. Adapta las referencias culturales apropiadamente. No traduzcas la clave del encabezado title; no traduzcas el HTML de la imagen.