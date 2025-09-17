---
title: "Operations"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/NQXV586afr8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## Crear un array

Los arrays se usan para almacenar múltiples valores en una sola variable, en vez de declarar variables separadas para cada valor. Para declarar un array, define el tipo de la variable con corchetes.

```js javascript
String[] restaurants;
```
Ahora hemos declarado una variable que contiene un array de cadenas. Para insertar valores en él, podemos usar un literal de array: coloca los valores en una lista separada por comas, entre llaves:

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "Subway"};
```

Para crear un array de enteros, podrías escribir:

```js javascript
int[] myNum = {10, 20, 30, 40};
```
<hr>

## Acceder a elementos de un array

Accedes a un elemento de un array refiriéndote al número de índice. Esta instrucción accede al valor del primer elemento en restaurants:

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "Subway"};
System.out.println(restaurants[0]);

// El sistema mostrará "Burger King"
```

<hr>

## Cambiar un elemento de un array

Para cambiar el valor de un elemento específico, refiérete al número de índice:

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "Subway"};
System.out.println(restaurants[0]);
// El sistema mostrará "Burger King"

restaurants[0] = "McDonalds";
System.out.println(restaurants[0]);
// El sistema ahora mostrará "McDonalds"
```

<hr>

## Obtener la longitud de un array

Para saber cuántos elementos tiene un array, usa la propiedad `length`:

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "Subway"};
System.out.println(restaurants.length);
// El sistema mostrará 4
```
<hr>

## Recorrer un array

Puedes recorrer los elementos del array con el bucle `for`, y usar la propiedad `length` para especificar cuántas veces debe ejecutarse el bucle. El siguiente ejemplo imprime todos los elementos del array restaurants:

```js javascript
String[] restaurants = {"Burger King", "Chipotle", "Panda Express", "Subway"};
for (int i = 0; i < restaurants.length; i++) {
    System.out.println(restaurants[i]);
}

// Salida:
// Burger King
// Chipotle
// Panda Express
// Subway
```