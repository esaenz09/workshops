---
title: "Model Fit"
prereq: "Python"
icon: ""
draft: false
weight: 4
---

# ¿Se ajusta nuestro modelo?

Recuerda que la ecuación lineal que construimos tiene un valor de error aleatorio (**ε**).

<h3>
\[
    SALARY = 9449.96(XP) + 25792.20 + ε
\]
</h3>

Dado que **ε** es un valor de error que no podemos determinar, necesitamos preguntarnos:

1. ¿Qué tan bien representa nuestro modelo la realidad o qué tan bien `se ajusta` a los datos que tenemos?
2. ¿Cómo podemos saber si **Years of Experience** realmente tiene un efecto sobre el **Salary**?

Hay muchas maneras de responder esto, pero en el mundo del machine learning y la estadística existe un valor que podemos usar. Este valor se llama **R-Squared** o **R<sup>2</sup>**.

[R-Squared](https://www.ncl.ac.uk/webtemplate/ask-assets/external/maths-resources/statistics/regression-and-correlation/coefficient-of-determination-r-squared.html#:~:text=6%20See%20Also-,Definition,line%20approximates%20the%20actual%20data.) - es una medida que proporciona información sobre la bondad de ajuste de un modelo. En el contexto de la regresión, es una medida estadística de qué tan bien la línea de regresión aproxima los datos reales. Como regla general, si el valor de **R<sup>2</sup>** está cerca de 1, significa que el modelo matemático elegido tiene un buen ajuste o realmente aproxima los valores reales en nuestros datos.

## Ejercicio 1: Encontrando R-Squared

El archivo `Experience_vs_Salary-More_Data` tiene más de 10,000 entradas donde puedes ver el salario y los años de experiencia de empleados de la empresa para la que trabajas. El código de Replit a continuación tomará la muestra inicial de 30 empleados y calculará el error estándar y el R<sup>2</sup>.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/04-e1.py" target="_blank">Launch Replit</a>

Como puedes ver, el valor de R<sup>2</sup> es 0.973. Ahora, si alguien nos pregunta si existe alguna relación en nuestros datos, podemos decir que "estamos 97.3% seguros de que los años de experiencia de un empleado están relacionados con el salario que percibe".

Te animo a cambiar la variable 'sample_size' a un tamaño mayor o menor para ver cómo se ve afectado el valor de R<sup>2</sup>.

¡Ahora vamos a hacer algunas predicciones!