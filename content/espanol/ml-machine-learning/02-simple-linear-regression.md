---
title: "Simple Linear Regression"
description: "Hacer que las computadoras aprendan a predecir resultados."
prereq: "Python"
icon: ""
draft: false
weight: 2
---

# ¿Qué es la regresión lineal simple?

La regresión lineal simple tiene como objetivo encontrar una correlación entre dos variables y derivar ecuaciones matemáticas que expliquen la relación entre una variable dependiente y una independiente. Con la regresión lineal simple, en general, queremos llegar a la siguiente conclusión:

1. ¿Existe una **relación** entre las variables que tenemos?

    Puedes determinar la relación entre ingresos y gastos, experiencia y salario, o humedad y temperatura. Pero, por ejemplo, NO existe relación entre la estatura de un estudiante y sus calificaciones en un examen.

2. ¿Podemos **predecir / pronosticar** valores con esto?

    Con la regresión, podemos entrenar el modelo y averiguar si podemos predecir valores con cierta certeza. ¿Podemos usar lo que sabemos sobre la relación para predecir nuevos valores?
    
    Ejemplo: ¿Cuál será la temperatura mañana? ¿Cuánto venderá mi panadería este año comparado con el año pasado? ¿Cuánto será mi salario si tengo 5 años de experiencia?

# Roles de las variables

En la regresión lineal simple, las variables pueden tomar uno de 2 roles.

1. **Variable dependiente**

    La variable cuyo valor queremos predecir o pronosticar. La llamamos **dependiente** porque su valor depende de otra cosa. Llamaremos a esta variable **y**.

2. **Variable independiente**

    Es la variable que podemos controlar o cambiar para afectar a la variable dependiente. Llamaremos a esta variable **x**.

    Ejemplo: Si una manzana cuesta $1.00 y compras 10, el costo total será $10.00. La variable dependiente aquí es el `costo total` mientras que la variable independiente es el número de manzanas que quieres comprar.

# El modelo matemático de la ecuación lineal simple

Cuando usamos regresión lineal simple la llamamos **lineal** porque, bueno... el modelo matemático representa una línea recta en un plano 2D. Pensemos en ello por un segundo.

¿Cuál es la ecuación matemática de una línea recta?

{{% expand "**Haga clic para ver la respuesta**" %}}

Esta ecuación puede resultarte muy familiar. Si es así, es la ecuación general de una línea recta.

<h1>
\[
    y = ax + b
\]
</h1>

- **x** es la variable independiente.
- **y** es el valor dependiente.
- **a** es la pendiente de la línea.
- **b** es la ordenada al origen o el valor de **y** cuando **x = 0**.

Partiendo de esta ecuación, explicaremos cómo los modelos matemáticos de la regresión lineal simple calculan y predicen nuevos valores.

{{% /expand %}}

# Ejemplos del mundo real

En el mundo real, los datos a veces no son lineales y se comportan distinto a lo que pensamos. A primera vista puede parecer que los datos no tienen ninguna relación. En el caso de la regresión lineal simple, lo que debes buscar es datos que más o menos sigan un patrón lineal.

Supongamos que trabajas como `Analista de datos` para el departamento de recursos humanos de una empresa que tiene más de 10,000 empleados. Tu jefe quiere saber si los años de experiencia de un empleado tienen alguna relación con la cantidad de dinero que gana. Por supuesto, como `Analista de datos` puedes consultar la base de datos de empleados y verificar rápidamente lo siguiente:

1. ¿Cuál es su salario actual?
2. ¿Cuántos años de experiencia tiene la persona?

Asume que puedes obtener datos de 30 empleados al azar que se ven algo así:

|Employee ID|Years of Experience|Salary|
|:--:|:--:|:--:|
|1|1.1|39343|
|2|1.3|46205|
|3|1.5|37731|
|4|2.0|43525|
|5|2.2|39891|
|6|2.9|56642|
|7|3.0|60150|
|8|3.2|54445|
|...|...|...|
|26|9.0|105582|
|27|9.5|116969|
|28|9.6|112635|
|29|10.3|122391|
|30|10.5|121872|

Después de revisar la tabla, trazas todos estos valores en un diagrama de dispersión 2D y obtienes una imagen como esta.

|![Years of Experience vs Salary](../resources/Years_vs_Salary.png)|
|:--:|
|Scatter Plot: Years of Experience vs Salary.|

Como puedes ver, los puntos se parecen _algo_ a una línea. Dibujemos una línea imaginaria y veamos si podemos pasar por todos los puntos.

|![Years of Experience vs Salary with Trendline](../resources/Years_vs_Salary_with_trendline.png)|
|:--:|
|Scatter Plot: Years of Experience vs Salary with line.|

Como puedes ver, la línea no pasa por **TODOS** los puntos, pero está parcialmente cerca. ¿Qué significa esto? ¿Por qué en algunos casos los puntos están más cerca o más lejos de nuestra línea imaginaria?

Hasta ahora sabemos que:

1. Los datos siguen en cierto modo un enfoque **lineal**.
2. Los datos tienen 2 variables importantes: **SALARIO** y **AÑOS DE EXPERIENCIA**. Esto significa que podemos comenzar a **modelar** nuestra relación como una ecuación lineal.

**Pregunta:** Sabemos que **SALARIO** y **AÑOS DE EXPERIENCIA** son nuestras variables, ¿pero cuál es la dependiente y cuál la independiente?
{{% expand "**Haga clic para ver la respuesta**" %}}

- **AÑOS DE EXPERIENCIA (XP)** es nuestra variable independiente.
- **SALARIO** es nuestra variable dependiente.

Si las colocamos en nuestra ecuación lineal obtendremos algo así:

<h1>
\[
    SALARIO = a(XP) + b
\]
</h1>

Con una ecuación como esta estamos diciendo: "Los años de experiencia tienen un efecto directo en el salario de un empleado".

{{% /expand %}}

# La posibilidad de errores

Como mencionamos antes, los datos pueden no ser siempre consistentes y pueden comportarse de distintas maneras. Esto significa que nuestra ecuación lineal debe considerar un posible error. Pero, ¿cómo representamos ese error en la ecuación? ¿Cómo se visualiza ese error en el diagrama de dispersión?

Supongamos que todos los empleados elegidos en la tabla anterior son de San Antonio, TX, pero el departamento de RR. HH. accidentalmente añadió empleados de la ciudad de Seattle, WA al conjunto de datos que seleccionaste. [El costo de vida en Seattle es un 28.6% más alto que en San Antonio](https://www.numbeo.com/cost-of-living/compare_cities.jsp?country1=United+States&country2=United+States&city1=Seattle%2C+WA&city2=San+Antonio%2C+TX&tracking=getDispatchComparison). Esto explicaría por qué algunos puntos de datos en el gráfico están más alejados de la línea imaginaria que trazamos. Estos se consideran errores en nuestros datos.

<!-- TODO: Add diagram to replace the figure below.-->
|![Error Lines for Simple Linear Regression](../resources/error-lines.svg)|
|:--:|
|Error Lines for Simple Linear Regression|

En nuestra ecuación lineal, añadamos ese error con la letra griega **ε**.

<h1>
\[
    SALARIO = a(XP) + b + ε
\]
</h1>

**ε** es el posible error que pueden tener nuestros datos. Lo que la `regresión lineal simple` intenta hacer es dibujar una línea imaginaria que minimice este error entre los puntos de datos. Este error es un valor que a menudo se ignora, pero lo importante es que nuestra ecuación lineal lo considerará y podemos representar la ecuación de forma familiar para nuestro ejemplo.

# Ejercicio 1: Jugando con Scikit-learn

Scikit-learn es una biblioteca de machine learning que nos ayudará a analizar y usar el modelo de regresión lineal simple incorporado para predecir datos. En la ventana de Replit más abajo, puedes ejecutar el programa `02-e1.py` que utilizará un conjunto de datos de empleados junto con sus años de experiencia. El programa trazará una muestra de 30 empleados de los empleados dentro de la empresa:

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/02-e1.py" target="_blank">Abrir Replit</a>

# Ejercicio 2: Encontrando la pendiente y la ordenada al origen

Antes de continuar, analicemos nuestra ecuación una vez más. Sabemos que nuestra ecuación se ha actualizado así:

<h1>
\[
    SALARIO = a(XP) + b + ε
\]
</h1>

Hemos podido determinar cuáles son los valores de **x** e **y**, pero ¿qué pasa con **a** y **b**? Recordemos qué significa cada uno de los valores que faltan:

- **a** es la pendiente o coeficiente de la línea. La **pendiente** representa el cambio estimado en la variable dependiente, en este caso, el **SALARIO**.
- **b** es la ordenada al origen o el valor de **y** cuando **x=0**. Después de trazar nuestro conjunto de datos, puedes ver cuál sería el valor del **SALARIO** cuando los **AÑOS DE EXPERIENCIA** son 0.

¿Un momento? Si ingreso a la empresa sin experiencia, ¿mi salario será 0? Eso no suena correcto. Vamos a averiguar cuál es el valor real. 

Usando scikit-learn podemos utilizar el modelo de regresión lineal y encontrar el valor de **a** y **b**. En la ventana de Replit más abajo, analicemos el código.

Primero, necesitamos importar los datos del archivo CSV:

```python
# Importar el conjunto de datos
dataset = pd.read_csv("Experience_vs_Salary.csv")
x = dataset.iloc[:, :-1].values # Obtener todos los valores de "Experience"
y = dataset.iloc[:, 1].values # Obtener todos los valores de "Salary"
```

Luego creamos una instancia de la clase `LinearRegression` y **ajustamos** el modelo a los datos. La función `fit` analizará los valores de nuestro archivo CSV y encontrará los valores de **pendiente** y **ordenada al origen**.

```python
model = linear_model.LinearRegression()
model.fit(x,y)
```

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/02-e2.py" target="_blank">Abrir Replit</a>

Como puedes ver, el código ha devuelto el valor del **coeficiente** y de la **ordenada al origen** de nuestra ecuación lineal. Vamos a actualizar nuestra ecuación lineal con esto.

<h3>
\[
    Intercept = 25792.20
\]
\[
    Coefficient= 9449.96
\]
\[
    SALARIO = 9449.96(XP) + 25792.20 + ε
\]
</h3>

Sabemos que el modelo nos dio una ordenada al origen de **25792.20**. Esto significa que un empleado SIN experiencia tendría un salario de $25792.20. ¿Pero qué significa 9449.96? Esto significa que, por cada año de experiencia, el salario de los empleados aumenta en 9449.96. Pero espera un momento, ¿cómo podemos asegurarnos de que estos son los valores correctos? ¿Tenemos confianza en que éstos sean de hecho los valores correctos? Si tomamos otros 30 empleados al azar y verificamos sus salarios, ¿obtendremos los mismos valores?