---
title: "Introduction"
date: 2022-08-06T13:24:17-07:00
draft: false
weight: 1
---

Los árboles están formados por dos componentes: **edges** y **nodes**. Veamos cada uno de estos componentes con un poco más de detalle.

### Aristas

Puedes imaginar una **edge** como la línea que conecta dos **nodes**. Las **edges** siempre conectan exactamente dos **nodes**. Las **edges** pueden transportar algo de información, pero no es obligatorio.

### Nodos

Los **nodes** son simplemente puntos en un árbol que representan algunos datos. Un árbol necesita al menos un **node** y cada **node** puede tener tantas **edges** como quiera, siempre que exista otro **node** distinto al que esté conectado.

### ¿Por qué los árboles?

Los árboles son estructuras de datos muy simples que pueden almacenar gran cantidad de información y, aun así, permitir encontrarla rápidamente. Muchos algoritmos que dependen de encontrar la mejor coincidencia organizan sus datos en un árbol antes de buscar para optimizar su velocidad. Algunos ejemplos de uso de árboles en el mundo real incluyen:
* <a href="https://en.wikipedia.org/wiki/Spanning_Tree_Protocol" target="_blank">Spanning Tree Protocol</a> - Un protocolo fundamental para el uso de Internet,
* <a href="https://en.wikipedia.org/wiki/Binary_search_algorithm" target="_blank">Binary Search</a> - Uno de los algoritmos más eficientes para buscar datos en un conjunto ordenado,
* <a href="https://docs.oracle.com/javase/8/docs/api/java/util/TreeMap.html" target="_blank">TreeMaps</a> - El complemento del HashMap en Java que usa un árbol para organizar los datos

Algunos árboles tienen reglas más específicas sobre cómo se agrega la información y cómo se mantiene internamente, lo que significa que casi siempre existe un tipo de árbol adecuado para cada escenario.

## Visualizando árboles

Los árboles tendrán lo que se llama un **root node**, que es el **node** al que se conecta el resto del árbol, ya sea de forma directa o indirecta. Llamamos a esta estructura de datos un árbol porque los **nodes** se ramifican a partir del **root node**. Cuando ves un árbol dibujado, normalmente verás el **root node** en la parte superior, ¡pero eso no siempre será así!

![image](../img/tree.png)