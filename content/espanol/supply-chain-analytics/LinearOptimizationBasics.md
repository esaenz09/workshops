---
title: "Linear Optimization - The Basics"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 3
---

## ¿Qué es la optimización?
Definición oficial: Un modelo de optimización matemática consiste en una función objetivo y un conjunto de restricciones en forma de un sistema de ecuaciones o desigualdades.

La optimización lineal puede sonar realmente complicada —y puede serlo. Pero para empezar, realmente solo necesitas entender unas pocas cosas.

## Optimización

La optimización es la forma de tomar la decisión más eficiente cuando tienes recursos limitados. Por ejemplo, cuando solo tienes una cantidad limitada de tiempo para jugar en tu consola, querrás asegurarte de jugar tu juego favorito la mayor parte de ese tiempo para usar tu tiempo de manera eficiente.

En un problema de optimización, estás escribiendo una fórmula matemática para representar restricciones del mundo real, como el tiempo de computación o el número de huevos. (¡Supongo que sí usamos álgebra después de todo!)

Hoy en día, puedes usar Excel o Python para resolver estos problemas sin tener que escribir las ecuaciones tú mismo.

Hay 3 partes principales que necesitas aprender: decision variables (variables de decisión), objective function (función objetivo) y constraints (restricciones).

## Decision Variables

Estas son las variables que deseas optimizar (por ejemplo, el número de huevos). La computadora las resolverá por ti y recomendará la cantidad óptima.
 
<img src= ../img/decision_var.jpg alt="Image showing the two types of cookies with #1 and #2 written" width="600" height="300">

## Objective Function

Esta es la ecuación que describe cuál es tu objetivo. Por ejemplo, puedes querer maximizar la cantidad de dinero que ganas en tu panadería. ¿Cómo calculas la cantidad de dinero que ganarás? Es la ganancia por cada galleta multiplicada por el número de galletas que producirás (¡aquí es donde entran las decision variables!).

![Image that shows the calculation of the objective function using the pictures of the cookies and the pictures of money](../img/objective_function.jpg)

## Constraints

Estas son las limitaciones que tienes. Por ejemplo, si dispones de un número limitado de huevos, debes asegurarte de que el total de huevos que uses sea menor o igual al número de huevos disponibles. Así es como se forma la ecuación.

![Image that shows the constraint function in terms of pictures of cookies and pictures of eggs](../img/constraint_equation.jpg)