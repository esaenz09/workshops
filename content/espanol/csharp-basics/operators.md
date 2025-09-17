---
title: "Operators"
description: "Introduce operadores y realiza operaciones sobre variables en C#."
date: 2024-09-16T00:00:00Z
weight: 5
---

## Hagamos matemáticas: Operador Aritmético

En el ejercicio anterior, aprendimos sobre variables y cómo podemos asignar valores a una variable de un tipo específico, por ejemplo:

```C#
int age = 3;  // declara la variable age de tipo int con valor 3
age = 4;      // asigna 4 a la variable age
```

Al mirar el código anterior, esencialmente suma 1 al valor de la variable `age`. 

Y, en C#, podemos realizar operaciones matemáticas sobre variables directamente con los **operadores aritméticos**: `+`, `-`, `*`, `/`, `%`.
Por ejemplo, podemos usar el operador de suma `+` para sumar 1 a `age`:

```c#
int age = 3;  // declara la variable age de tipo int con valor 3
age = age + 1;// suma 1 a age
```

{{% notice note %}}
Los siguientes son los operadores aritméticos en C#:

**Operador** | **Descripción** | **Ejemplo**
------|------|--------
`+` | suma | `1 + 1 = 2`
`-` | resta | `2 - 1 = 1`
`*` | multiplicación | `3 * 3 = 9`
`/` | división | `9 / 3 = 3`
`%` | módulo/resto | `10 % 4 = 2`

**Nota**: Si ambos operandos de una división son enteros, el resultado también será un entero. Por ejemplo, `10 / 4` devuelve 2, no 2.5 ya que descartamos el resto. Si cualquiera de los operandos es un double, el resultado será un double.

**Nota**: Usa la operación módulo (`%`) para obtener el resto de la operación de división.

{{% /notice %}}

{{% notice tip %}}
El operador de suma (`+`) se usa en Strings como operador de concatenación. Por ejemplo:

`String name = "Patric" + "k";` es lo mismo que `String name = "Patrick";`
{{% /notice %}}

### Instrucciones
1. Usa el programa de abajo para practicar usando los operadores aritméticos. Cambia los números para ver las respuestas.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/dUSTOt" frameborder="0"></iframe>

## Comparaciones: Operador Relacional

A continuación, aprendamos cómo comparar números, usando **operadores relacionales**.

Al igual que en matemáticas, podemos comparar números usando `>`, `<`, `>=`, `<=`. Por ejemplo: `(3 > 2)` es `true`, un valor booleano.

{{% notice note %}}
Los siguientes son los operadores relacionales en C#:

**Operador** | **Descripción** | **Ejemplo**
------| ------| ------
`==` | igual a | `(3 == 3)` es `true`
`!=` | distinto de | `(3 != 3)` es `false`
`>` | mayor que | `(3 > 2)` es `true`
`<` | menor que | `(3 < 2)` es `false`
`>=` | mayor o igual que | `(3 >= 2)` es `true`
`<=` | menor o igual que | `(2 <= 2)` es `true`

Nota: `==` y `!=` solo pueden usarse con datos del mismo tipo. Por ejemplo:
```csharp
int x=3; 
double y=3.0; 
x==y; // Esto produciría un error porque x y y son de diferentes tipos.
```

{{% /notice %}}

{{% notice tip %}}
Usar 1 signo igual asigna un valor a la variable. Usar 2 signos iguales compara los valores de dos elementos.

```csharp
age = 3;  // establece el valor de age en 3
age == 3; // comprueba si el valor de age es 3
```
{{% /notice %}}

### Práctica de Comparación

1. Usa el programa de abajo para practicar usando los operadores de comparación. Cambia los números para ver las respuestas.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/tZs8tb" frameborder="0"></iframe>

## ¡Estadísticas del examen!

Patrick 🐥 y 4 de sus compañeros de clase acaban de tener un examen de música en esta clase. Estas son las notas de sus exámenes: Patrick(88), Tom(89), Mary(95), Chris(84), Jen(92).

Queremos producir un informe de calificaciones de toda la clase.

Este informe lista la calificación de cada estudiante, el promedio de la clase y si el promedio de la clase está por encima de 60, 70, 80, 90 (`true` o `false`), como el siguiente:

```
---------------------------
     Informe de Calificaciones de Música    
---------------------------

Calificaciones de los estudiantes:          
- Patrick: ...
- Tom: ...
...

Promedio de la clase: ...
- Promedio sobre 60: ...
- Promedio sobre 70: ...
- Promedio sobre 80: ...
- Promedio sobre 90: ...
```

¡Escribámoslo con la ayuda de los operadores 🎵!

{{% notice note %}}

### Instrucciones:

1. Identifica todas las variables en las sentencias de impresión y decláralas comenzando en la línea 12 con el tipo de dato correcto y el valor. Nota que hay 10 variables en total, y `average` ya ha sido declarado para ti).

   Pista: por ejemplo, la variable `patrickGrade` debería declararse y asignarse en la línea 13 como `int patrickGrade = 88;`.

2. Calcula el promedio correcto de la clase y asígnalo a la variable `average` usando **operadores aritméticos** tales como `+`, `-`, `*`, `/`, `%`. Asegúrate de usar paréntesis alrededor del número total de puntos.

   Ten en cuenta que una puntuación promedio es `(puntos totales)`/`(número de estudiantes)`.

3. Asigna las variables `over60`, `over70`, `over80`, `over90` con el valor correcto usando **operadores relacionales** tales como `>`, `<`, `>=`, `<=`.

4. Ejecuta el programa y ¡ve el informe impreso!

{{% /notice %}}

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/mM7xbj" frameborder="0"></iframe>