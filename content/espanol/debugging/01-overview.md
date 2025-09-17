---
title: "An Overview of Debugging"
difficulty: "Intermediate"
weight: 2
draft: false
---

Hay muchas formas diferentes de depurar un programa. En esta guía comenzaremos con algunos pasos generales para que no te pierdas al depurar un programa. Hay 3 pasos básicos para depurar un programa:

1. **Identificar el problema**. En este paso, tu objetivo es identificar qué está causando el bug. Esto implica encontrar las condiciones que llevaron al bug. Poder reproducir el bug te da parte de la información que necesitas, lo que te permite acotar el problema y, quizá, te ayuda a entender por qué el bug está ocurriendo en primer lugar.

2. **Encontrar una solución**. En este paso, tu objetivo es arreglar el bug. A veces este es el paso más sencillo, pero otras veces es difícil porque podrías descubrir que la lógica de tu programa estaba equivocada desde el principio. Este paso, combinado con el paso 3, puede fácilmente llevar la mayor parte del tiempo.

3. **Probar la solución**. Si tu arreglo en realidad no corrige el bug, ¿de qué servirá? También necesitas asegurarte de que tu arreglo no introduzca más bugs. Este paso puede ser tan simple como recompilar y ejecutar el programa de nuevo una vez que hayas aplicado la corrección. O puede implicar ejecutar toda una batería de pruebas automatizadas en un entorno. En cualquier caso, el objetivo de este paso es establecer la *corrección* del programa.

Sin duda, la parte más frustrante de la depuración es el paso 1. Como programadores, nuestro trabajo es escribir código, ¡pero no podemos escribir código para arreglar el problema si no sabemos cuál es el problema en primer lugar! Por eso, la mayor parte de este taller se centrará en encontrar dónde podría estar escondido un bug y en cómo puedes usar algunas herramientas para ayudar en tu búsqueda.