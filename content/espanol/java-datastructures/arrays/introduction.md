---
title: "Introduction"
date: 2019-07-23T11:45:38-07:00
draft: false
weight: 1
---

Arrays son una estructura de datos en la que cada uno de sus elementos está dispuesto en una secuencia numérica y cada elemento se referencia por su número de posición. En Java, cada uno de estos elementos es de un mismo tipo (`String`, `int`, `double`, etc.) y están indexados desde cero, lo que significa que el primer elemento en un array comienza en `0`, el segundo en `1`, y así sucesivamente.

![image](../img/array.png)

Aquí hay vocabulario importante que necesitarás conocer antes de que hablemos más sobre arrays.

- El número de elementos en un array se llama la **length** del array.
- El tipo de los elementos individuales en un array se llama el **base type** del array.
- El número de posición de un elemento en un array se llama el **index** de ese elemento.

Para nuestros propósitos, queremos crear un array que pueda contener todos los distintos restaurantes de nuestra app. Supongamos que nuestro programa necesitará procesar los nombres de mil restaurantes diferentes. Necesitaremos una forma de poder ordenar y manejar todos los datos. Sin una estructura de datos array, tendríamos que resolver el problema creando mil variables diferentes, una para cada restaurante, y si quisiéramos hacer algo tan sencillo como, por ejemplo, imprimir los nombres de cada restaurante, tendríamos que poner 1000 sentencias de impresión. Lograr esto sería todo un desafío.

Por el contrario, los arrays nos permiten hacer las mismas acciones, pero en un solo paso. El array es simplemente una única variable, pero contiene los 1000 restaurantes dentro de él.

![image](../img/array2.png)

La **length** del array sería 1000, ya que hay 1000 nombres individuales. El **base type** del array sería `String` ya que los elementos del array son strings. El primer nombre estaría en el **index** `0` del array, el segundo nombre en el **index** `1`, y así sucesivamente, hasta el nombre número mil en el **index** `999`.