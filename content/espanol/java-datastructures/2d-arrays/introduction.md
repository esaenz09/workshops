---
title: "Introduction"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 1
---

<p style="text-align: center;"><iframe width="60%" height="600px" src="https://youtube.com/embed/DZkUUk64mWM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## ¿Qué es un arreglo 2D?

Ya hemos aprendido bastante sobre arreglos. Sabemos que un arreglo puede contener muchos tipos distintos (enteros, cadenas, doubles, etc.), ¿pero qué pasa con un arreglo que contiene arreglos?

![image](../img/2darray.png)

Un arreglo 2D tiene un tipo como `int[][]` o `String[][]`, con dos pares de corchetes. Los elementos de un arreglo 2D se organizan en filas y columnas, y el operador new para arreglos 2D especifica tanto el número de filas como el número de columnas. Por ejemplo,

```js javascript
int[][] A;
A = new int[3][4];
```

Esto crea un arreglo 2D de `int` que tiene 12 elementos organizados en 3 filas y 4 columnas. También existen inicializadores para arreglos 2D. Por ejemplo, esta instrucción crea el arreglo de 3 por 4 que se muestra en la imagen de abajo:

```js javascript
int[][] A = {    
                {  1,  0, 12, -1 },
                {  7, -3,  2,  5 },
                { -5, -2,  2, -9 }
            };
```

Un inicializador de arreglo para un arreglo 2D contiene las filas de `A`, separadas por comas y entre llaves. Cada fila, a su vez, es una lista de valores separados por comas y entre llaves. También existen literales de arreglos 2D con una sintaxis similar que se pueden usar en cualquier lugar, no solo en declaraciones. Por ejemplo,

```js javascript
A = new int[][] { 
                    {  1,  0, 12, -1 },
                    {  7, -3,  2,  5 },
                    { -5, -2,  2, -9 }
                };
```
                  
Todo esto se extiende de forma natural a arreglos tridimensionales, de cuatro dimensiones e incluso a arreglos de dimensiones superiores.