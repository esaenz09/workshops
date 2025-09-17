---
title: "Confidence Interval"
description: "Haz que las computadoras aprendan a predecir resultados."
prereq: "Python"
icon: ""
draft: false
weight: 3
---

Desde la última sección pudimos encontrar el coeficiente y el intercepto de nuestra ecuación lineal usando un conjunto de datos de muestra de 30 empleados aleatorios.

<h3>
\[ 
    Intercept = 25792.20
\]
\[ 
    Coefficient= 9449.96
\]
\[ 
    SALARY = 9449.96(XP) + 25792.20 + ε
\]
</h3>

Pero esto planteó otra pregunta: ¿el **salary** REALMENTE está relacionado con los **years of experience** de un empleado? ¿Es la relación entre las dos variables lo suficientemente fuerte como para afirmar que están relacionadas? ¿Son 30 empleados aleatorios suficientes para determinar esto? ¿Cómo podemos asegurarnos de que estos son los valores correctos?

Debes recordar que encontraste los valores trabajando con una muestra pequeña que fue extraída de un número mucho mayor de empleados. Como solo tenemos una muestra con la que probar, los valores para el **coefficient** y el **intercept** tendrán más incertidumbre.

¿Qué podemos hacer para asegurarnos de que los valores son válidos?

{{% expand "**Click to show answer**" %}}

Necesitamos ejecutar el modelo lineal con más muestras aleatorias.

{{% /expand %}}

# Ejercicio 1: Comprobando más muestras

Supongamos que pudiste encontrar más de 10,000 registros de empleados dentro de tu empresa 😯. ¡Esto es increíble porque, en el mundo del aprendizaje automático, mientras más datos tengas mejores serán los resultados! Ahora tomemos 30 registros aleatorios de ese conjunto de más de 10,000 y comprobemos si los valores del intercepto y del coeficiente difieren de la muestra original que teníamos. En la ventana de Replit abajo ejecuta el código tantas veces como quieras, pero observa cómo los valores del **intercept** y del **coefficient** son algo similares a los que calculamos antes.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/03-e1.py" target="_blank">Abrir Replit</a>

¿Por qué está pasando esto? ¿Por qué los valores del **intercept** y del **coefficient** son diferentes cada vez? ¿Por qué la línea de la muestra original (es decir: línea verde) está muy cerca de la línea azul (es decir: la nueva muestra)?

{{% expand "**Click to show answer**" %}} 
Esto ocurre porque cada vez que ejecutas el programa se selecciona una muestra aleatoria de 30 registros. En cualquier muestra aleatoria que tomes, ambos valores serán distintos. Pero lo bueno es que todos estos valores se obtienen del mismo conjunto de datos.

{{% /expand %}}

Ahora pregúntate, ¿qué tan **seguro** estás de que los valores del **intercept** y del **coefficient** realmente representan los datos que tenemos?

# Intervalos de confianza

El ejemplo anterior nos enseña que, cuando trabajas con muestras aleatorias de un conjunto de datos más grande, los valores del **intercept** y del **coefficient** caen dentro de un rango. Sabemos que el valor real debe estar entre dos valores pero no sabemos cuáles son. Esto se conoce como [intervalo de confianza](https://www.geeksforgeeks.org/confidence-intervals-for-machine-learning/).

Cuando ejecutas el código del **Ejercicio 1** varias veces puedes ver que el valor del **coefficient** cambia cada vez, pero fíjate cómo rara vez cae por debajo de 9000 o rara vez supera 10000. ¿Cuál es la diferencia entre todos los posibles **coefficients** que podemos encontrar ejecutando el código múltiples veces? ¿Cuál es ese valor? Esto se conoce como el **error estándar**.

[Standard Error](https://www.statology.org/standard-error-regression/) - la distancia promedio que los valores caen desde la línea de regresión.

# Ejemplo 2: Encontrando el error estándar

Podemos usar la librería [StatsModels](https://www.statsmodels.org/stable/index.html) para obtener todo tipo de valores de nuestra regresión lineal. Ejecuta el Replit a continuación y deberías ver una salida como esta:

|![Statmodels result](../resources/finding_stderror.png)|
|:--:|
|Summary of Statsmodel run|

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/03-e2.py" target="_blank">Abrir Replit</a>

Dentro de la tabla centrémonos en el error estándar, que es el valor etiquetado como **stderr**. En este caso es **409.40**. Esto significa que, para cualquier conjunto de muestra aleatoria, el **coefficient** o la **slope** de nuestra línea variará en 409.40 o, en otras palabras:

“El salario de un empleado puede variar en $409.40.”

# Ejemplo 3: La distribución normal

Hagamos un paso atrás y pregúntate: de entre los coeficientes o pendientes que podemos ver en el "Ejercicio 2", ¿qué tan probable es que se repitan al ejecutar el programa con otras muestras?

El aprendizaje automático utiliza muchas estadísticas para determinar los valores que hemos obtenido. En el mundo de la estadística existe un gráfico usado para medir la probabilidad de que un valor aparezca en los datos. Esto se conoce como la `Distribución Normal` o `Curva de campana` y se parece a esto:

|![Normal Distribution](../resources/normal_distribution.png)|
|:--:|
|Figure #: Normal Distribution or Bell Curve|

Tomemos el siguiente ejemplo: ¿qué tan probable es ver a una persona muy baja? ¿qué tan probable es ver a una persona muy alta?

Si representamos esto con una curva de campana obtendrás algo así:

|![Normal Distribution](../resources/normal_distribution_height.png)|
|:--:|
|Figure #: Normal Distribution or Bell Curve with people's height.|

Como puedes ver, es muy improbable ver a una persona muy baja o muy alta. Pero es bastante normal ver personas de estatura promedio. Claro que esto puede variar según el país, pero te haces la idea.

Si ejecutas el Replit abajo verás cómo el histograma generado se asemeja a la curva de campana. El programa crea un [histograma](https://corporatefinanceinstitute.com/resources/excel/histogram/) que muestra la cantidad de veces que un valor aparece en nuestro conjunto de datos. Es decir, varios empleados con el mismo salario.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/03-e3.py" target="_blank">Abrir Replit</a>

Cuando esto sucede podemos usar el error estándar y la siguiente ecuación para decir: "Estamos 95% seguros de que el valor del coeficiente estará en este rango". Pero, ¿cuál es ese rango? Este rango es nuestro **intervalo de confianza**.

<h3>
\[ 
    CoefficientRange = Coefficient \pm2 * (StdError)
\]
</h3>

Como sabemos que el error estándar es 409.40 podemos calcular el rango del coeficiente así:

<h3>
\[ 
    StdError = 409.40
\]
\[ 
    Coefficient = 9449.96
\]
\[ 
    CoefficientRange = Coefficient \pm 2 * StdError
\]
\[ 
    CoefficientRange = 9449.96 \pm 2 * StdError
\]
\[ 
    CoefficientRange = [8,631.16, 10,268.76]
\]
</h3>

Lo que estamos diciendo con el **rango del coeficiente** anterior es:

- "El valor del **coefficient** estará entre 8,631.16 y 10,268.76."
- "El aumento del salario de un empleado por año está entre 8,631.16 y 10,268.76."

El código abajo tomará una muestra de 100 empleados aleatorios y creará histogramas para mostrar cómo se asemejan a una curva de campana. Como puedes ver, los valores casi nunca se salen del rango del coeficiente.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/03-e3.py" target="_blank">Abrir Replit</a>