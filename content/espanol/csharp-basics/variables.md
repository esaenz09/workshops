---
title: "Variables and Data Types"
description: "Introduce tipos y variables en C#."
date: 2024-09-16T00:00:00Z
weight: 4
---

## Variables: ¡Nómbralo!

En el primer ejercicio, aprendimos a imprimir diferentes mensajes con `Console.WriteLine()` y `Console.Write()`.

Aunque está bien imprimir un número o una frase, no les hemos dado un significado y si quisiéramos usar la frase o el número de nuevo, tendríamos que escribirlos otra vez.

En C#, introducimos la idea de una **variable** para los datos. Una variable almacena un dato con un nombre.

Por ejemplo, puede haber una variable llamada `myName` a la que se le asigna el valor `"Ann"`. Otra variable podría llamarse `age` y se le asigna el número `12`.

## ¡Qué tipo!

¿Entonces, cómo creamos estas variables en C# para almacenar datos?

Antes de aprender a crear variables, necesitamos entender el concepto de **tipo de dato** en C# o simplemente **tipo**. El tipo en C# describe qué se está almacenando. Si tienes una variable de números, solo puede contener números, no frases ni símbolos. Cada variable tiene su propio tipo que controla qué clase de datos puede contener.

Por ejemplo, podríamos tener una variable llamada `age` que almacena el número `12`. Si intentas guardar la palabra `"twelve"` en `age` generará un error porque solo conoce números.

En C#, para que una variable almacene números enteros, usa el tipo `int`. Declaramos una variable `int` llamada `age` con el valor `12` con la línea de código:

```
int age = 12;
```

En general, para declarar una variable las escribimos en el formato: `[data type] [variable name] = [data];`.
{{% notice note %}}
Los siguientes son los tipos de datos importantes que vienen incorporados en C#:

**Tipo** | **Descripción** | **Ejemplos**
--------|-----------|----------
`int` | entero | `20`, `30`, `35`
`char` | carácter, como un símbolo o una sola letra del alfabeto | `'A'`, `'b'`, `'('`, `']'`
`string` | una secuencia de `char` | `"Hello"`, `"Bonjour"`, `"Hola"`
`bool` | booleano, tiene un valor `true` o `false` | `true`, `false`
`double` | números con fracción | `2.0`, `3.14`, `9.33`

{{% /notice %}}

Usando nuestro ejemplo anterior, para declarar estas variables en C#, escribimos lo siguiente:

```C#
string name = "Ann";
int age = 12;
boolean loveMusic = true;
```

La última variable es interesante. Solo puede tener un valor de `true` o `false`. Veremos que esto puede ser muy útil en las secciones más avanzadas de este taller.

## Juega con variables

Veamos qué podemos hacer con las variables.

En el .NET Fiddle siguiente, bifurca el Fiddle y prueba ingresando estas líneas y **ejecuta**:

```C#
int age = 10;
Console.WriteLine(age); // imprime 10
age = 12; // asigna el valor 12 a la variable age
Console.WriteLine(age); // imprime 12
```

Podemos asignar un valor a una variable, referenciarla y luego cambiar el valor.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/PPCCzG" frameborder="0"></iframe>

## ¡Qué tipo! — ¡Ayuda a Patrick!

Patrick 🐥 no es un experto en tipos de datos. A menudo los confunde al declarar variables. Ayudémosle a corregir sus errores en el .NET Fiddle a continuación.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/xKMKvn" frameborder="0"></iframe>