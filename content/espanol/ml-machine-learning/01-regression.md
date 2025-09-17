---
title: "What is regression?"
description: "Make computers learn to predict outcomes."
prereq: "Python"
icon: ""
draft: false
weight: 1
---

# ¿Qué es la regresión?
La regresión es una técnica para modelar la relación entre una característica (variables independientes) y una predicción (variables dependientes). Nos ayuda a entender cómo cambia el valor de una variable dependiente en función del valor de la variable independiente. ¡Cuando se aplica correctamente nos ayuda a predecir valores 😯!

<!-- TODO: Add diagram to replace image below. -->
|![Regression](../resources/regression.png)|
|:--:|
|Regression|

La regresión es una técnica poderosa que nos permite encontrar una línea o una curva que se ajusta a los datos que tenemos. Al hacer regresión, podemos crear o reutilizar `modelos matemáticos` que muestran cómo se relacionan las variables dependientes e independientes. [Los modelos matemáticos](https://www.youtube.com/watch?v=xHtsuOB-TPw) son útiles porque nos ayudan a comprender un sistema y hacer predicciones basadas en las variables del sistema. A veces, el modelo matemático que elegimos puede no ajustarse bien a los datos, por lo que debemos buscar un mejor modelo que capture los patrones que observamos.

## Ejemplo 1: ¿Cómo sabemos si va a llover?
Cuando usas tu teléfono, ves un noticiero, o simplemente preguntas en internet "¿Cuál es la probabilidad de lluvia hoy?", los meteorólogos usan modelos matemáticos para predecir si habrá posibilidad de lluvia. Tal vez te preguntes, ¿qué `variables` se toman en cuenta al ejecutar esos modelos matemáticos? ¿Será suficiente con el olor a lluvia?

{{% expand "**¿Qué variables deberías considerar para saber si va a llover?**"%}}

- Temperatura → ¿Hace calor, frío o está en el punto ideal?
- Altitud → Dependiendo de qué tan alto estés respecto al nivel del suelo, los lugares pueden ser más fríos o más cálidos.
- Ubicación → Dónde estés importa. (por ejemplo: bosque, playa, cordillera, desierto, etc.)
- Humedad → ¿Sientes que el aire está pesado? ¿Hay suficiente agua en el aire para que llueva?
- Época del año → ¿En qué mes estamos? ¿En qué estación estamos?
- ¡Y muchas más!

Hay muchas más variables a considerar cuando pensamos que hay posibilidad de lluvia. Al final del día, la "probabilidad de lluvia" es la variable dependiente, mientras que las otras propiedades que mencionamos arriba son las variables independientes. La probabilidad de lluvia depende de los valores de las demás variables mencionadas.
{{% /expand %}}

### Ejercicio 1
Supón que alguien quiere saber el tipo de figura que tiene basándose en el área de la figura.

1. ¿Eso es siquiera posible? ¿Se puede saber qué figura es basándose solo en el área?
{{% expand "**Haz clic para ver la respuesta**" %}}  
***No***, como puedes adivinar rápidamente, no hay relación única entre el **área** y el tipo de figura que pueda tener una figura.

Por ejemplo, un cuadrado de lado 3 tiene un área de 9.

<h3>
\[ 
    3 \cdot 3 = 9
\]
</h3>

Pero también un triángulo con base 6 y altura 3 tiene área 9.
<h3>
\[ 
    (6 \cdot 3)/2 = 9
\]
</h3>

{{% /expand %}}
<br>

2. Si el área no es una buena variable o propiedad para entender el tipo de figura que tenemos, ¿qué relación podemos usar para saber el tipo de figura?
{{% expand "**Haz clic para ver la respuesta**" %}}  

***¡El número de **lados** que tiene! A medida que aumenta el número de lados, puedes identificar el tipo de figura.***

Si te fijaste en nuestra tabla, hemos construido una relación lineal que puede representarse como X=Y.

X → **el número de lados**
Y → **tipo de figura**

¡Ahí lo tienes, creaste tu primer modelo de aprendizaje automático!
{{% /expand %}}
<br>

Un modelo, en el caso de nuestro ejemplo anterior, es simplemente una función que se construye para establecer una relación entre nuestra variable dependiente y las variables independientes. Por ejemplo, funciones tales como rectas (y = ax + b), parábolas (y = a(x - h)^2), curvas cúbicas (y = ax^3 + bx^2 + cx + d), y muchas más pueden usarse como modelos.

### ¿Cómo asegurarte de que tu modelo se ajusta a los datos?

Cuando realizamos análisis usando un modelo de aprendizaje automático existente necesitamos asegurarnos de seleccionar el modelo apropiado que represente de manera razonable nuestros datos. En la imagen de abajo puedes ver que los puntos de datos representan una parábola. Es muy probable que el modelo que necesitemos usar sea un modelo parabólico, algo como...

<h2>
\[ 
    y = a(x - h)^2
\]
</h2>

Cuando usas un modelo parabólico necesitas saber dónde caerán los vértices de la parábola para poder predecir dónde estará un nuevo punto. Podrías ejecutar un modelo sin ajustar vértices y terminar como en la imagen de "Under-fitting", o ajustar demasiados vértices y terminar como en la imagen de "Over-fitting". Queremos ajustarlo lo suficiente para que nuestro modelo "se ajuste" a los datos y nuevos puntos puedan ser representados usando el modelo.
 
<!-- TODO: Add diagram to replace image below. -->
|![Fitting Data Example](../resources/fitting-data-example.png)|
|:--:|
|Image 1: Under-Fitting and Over-Fitting|

Siempre debes asegurarte de que el modelo que eliges para representar tus datos se ajuste a lo que estás analizando. De lo contrario, podrías tener uno de dos problemas:
- Under-Fitting (Subajuste)
    
    Esto ocurre cuando no eres capaz de encontrar una relación en los datos que te han dado. Esto suele pasar cuando no hay suficientes datos para usar.

- Over-Fitting (Sobreajuste)
    
    Ocurre cuando intentas acomodar cada valor posible en tus datos, incluso aquellos que no representan nada. Al hacer esto, podrías estar eligiendo valores que son **outliers** y que no representan la realidad. Por ejemplo, tener una figura que tenga 1 o 2 lados no tiene sentido.