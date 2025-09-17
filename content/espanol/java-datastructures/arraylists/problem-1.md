---
title: "Problem 1: ArrayList Basics"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/unwrTbTILmA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<!--<link rel="stylesheet" href="../../style.css">-->

## Tarea 1: Inserción

¡Tacos Truck ahora está disponible en la calle! Los nuevos empleados tienen dificultades para llevar el control de todos los pedidos. ¡Ayúdales a organizar todos los elementos usando `ArrayList`s!

```js javascript
/*
Dan está pidiendo en su taquería favorita:
    - 2 pedidos de "carne asada"
    - 4 pedidos de "carnitas"
    - 1 pedido de "pollo"
    - 2 pedidos de "birria"

    Devuelve un ArrayList con todos estos elementos en ese orden
*/
```

{{% notice tip %}}
1. ¿Cómo puedes añadir elementos a la lista?
2. ¿Qué quiere Dan en el pedido?
{{% /notice %}}

<iframe frameborder="0" width="100%" height="800px" src="https://replit.com/@nuevofoundation/2DInsert?lite=true"></iframe>

## Tarea 2: Obtener elementos

Un restaurante de comida china acaba de abrir cerca. Ha llegado una gran cantidad de pedidos y al gerente le cuesta llevar el control de todo, así que lo han puesto todo en un `ArrayList`. Ayuda a terminar el programa para devolver la cadena dada en un índice dado.

```js javascript
ArrayList<String> menu = new ArrayList<>(); 

menu.add("Pizza"); 
menu.add("Hotdog"); 
menu.add("Hamburger"); 
menu.add("Hotdog"); 

// Devuelve "Pizza" ya que es el elemento 0 del menú
item = find(menu, 0);
```

{{% notice tip %}}
1. ¿Cómo puedes iterar por la lista?
2. ¡Mira el menú de ejemplo!
{{% /notice%}}

<iframe frameborder="0" width="100%" height="800px" src="https://replit.com/@nuevofoundation/2DFind?lite=true"></iframe>

## Tarea 3: Eliminación de elementos

¡El mismo restaurante de comida china tiene un error en su código! Los pedidos se han duplicado aleatoriamente y el `ArrayList` está lleno de copias de pedidos. Ayuda al dueño escribiendo un programa para eliminar las primeras `n` ocurrencias de un pedido dado en el `ArrayList`.

```js javascript
ArrayList<String> menu = new ArrayList<>(); 

menu.add("Pizza"); 
menu.add("Hotdog"); 
menu.add("Hamburger"); 
menu.add("Pizza");
menu.add("Pizza");
menu.add("Hotdog"); 

// Elimina los dos primeros pedidos de Pizza
item = remove(menu,"Pizza", 2);

// El menú no será el siguiente arreglo: {"Hotdog", "Hamburger", "Pizza", "Hotdog"}
```

<iframe frameborder="0" width="100%" height="800px" src="https://replit.com/@nuevofoundation/2DRemove?lite=true"></iframe>