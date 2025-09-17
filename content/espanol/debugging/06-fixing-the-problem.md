---
title: "Step 2 - Fixing the problem"
difficulty: "Intermediate"
weight: 7
draft: false
---

Una vez que hayas averiguado qué está causando el bug, puedes empezar a pensar en cómo arreglarlo. Los errores de compilación son bastante sencillos: la mayoría de las veces el compilador te da suficientes pistas sobre cómo solucionarlos, y cuando no puedes resolverlo solo con la salida del compilador, puedes recurrir a la web. Lo más probable es que alguien se haya topado con el mismo problema años atrás y ya lo haya preguntado en un foro como [StackOverflow](https://stackoverflow.com/).

Cuando se trata de corregir errores en tiempo de ejecución, depende de la aplicación que estás depurando. Querrás pensar en lo que hace tu programa, en lo que quieres que haga y en cómo escribir código para indicarle que haga lo que deseas.

Por ejemplo, una forma general de arreglar un bug de memoria es comprender que debes asegurarte de que el programa solo acceda a la memoria a la que tiene permiso. El lugar obvio para revisar es dónde ocurren los accesos a memoria. Desreferenciar punteros y/o usar índices de arreglos suele ser donde aparecen estos problemas. Como mostramos en la parte anterior, una herramienta como `valgrind` también es valiosa para encontrar fugas de memoria y los lugares donde tu programa puede estar fallando.

Para arreglar un programa que muestra un comportamiento extraño, el primer paso es comprobar si tu algoritmo o estrategia parece apropiado. El siguiente paso es verificar si tu programa realmente implementa el algoritmo correctamente. Más a menudo de lo que uno quisiera, un algoritmo complejo es difícil de implementar bien. Hay muchas implementaciones de algoritmos seguros en ciberseguridad, pero muchas de ellas tienen implementaciones defectuosas que las hacen inseguras.

Lo más importante es encontrar las preguntas correctas que hacerte mientras depuras. La técnica conocida como rubber duck coding consiste en que el programador habla en voz alta con un pato de goma; oírte explicar lo que estás haciendo puede hacer que descubras errores.

Desgraciadamente, arreglar un error suele ser algo extremadamente específico del programa. Es difícil ofrecer más que sugerencias generales.

{{% notice note %}}
Hay muchas herramientas que puedes usar para ayudar a encontrar un problema: los _linters_ están disponibles para la mayoría de los lenguajes y pueden detectar errores de sintaxis como problemas de formato, paréntesis faltantes y palabras clave mal escritas.

Con el avance de la inteligencia artificial (IA), herramientas como GitHub Copilot también pueden ayudar a sugerir soluciones para tus errores. Pero recuerda que las respuestas de la IA pueden ser incorrectas, ¡así que usa tu mejor criterio!
{{% /notice %}}