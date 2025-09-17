---
title: "Write to the Console"
description: "Introduce los métodos para imprimir en C#."
date: 2024-09-16T00:00:00Z
weight: 2
---

## Tu primer programa en C#

Nuestro primer ejercicio es familiarizarnos con la estructura de una aplicación sencilla en C# que escribe en la consola.

Intentemos ejecutar un programa en C# que imprima `Hello World` en la consola. La línea de código `Console.WriteLine ("Hello World");` hace esto por nosotros. Indica al ordenador que escriba en pantalla lo que esté entre los paréntesis ().

### ¡Escribamos algo de código!

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/0g4Vu7" frameborder="0"></iframe>

En el marco de .NET Fiddle de arriba, añade una nueva línea de código debajo de la primera línea para imprimir "Hello *tu nombre*". Debería verse algo así.

<img src="../images/Step1.png" height="300" alt="The starting screen of a fiddle" />

Deberías ver la salida en la parte inferior de la pantalla. ¿Genial, verdad?

Probemos a imprimir otras cosas. Añade algunas líneas adicionales de código para:
1. Imprimir números poniendo números dentro de los paréntesis (p. ej. `Console.WriteLine(42);`). No hace falta poner comillas dobles.
2. Juntar texto (p. ej. `Console.WriteLine("Hi " + "Sally");`)

{{% notice tip %}}
### ¿Notaste que todas las instrucciones que escribiste se imprimieron en líneas diferentes?

A veces queremos escribir en la misma línea. Usamos un código ligeramente diferente: `Console.Write` en lugar de `Console.WriteLine`.

Añade dos líneas de código:
```csharp
Console.Write("I like to eat ");
Console.Write("apples.");
```

Y pruébalo.
{{% /notice %}}

{{% notice warning %}}
### ¡¡Importante!! A veces no puedes simplemente poner caracteres entre " "

Al poner caracteres entre `" "` en una instrucción de impresión, a veces es fácil confundir al ordenador sobre qué caracteres imprimir.

Por ejemplo, ¿cómo le decimos al ordenador que imprima `"`?

Si escribes `Console.WriteLine(""");`, obtendrás un error porque el ordenador no puede identificar dónde termina el texto.

En su lugar, ciertos caracteres deben ser <b>escapados</b> añadiendo una `\` delante.

```csharp
Console.Writeline("\"");  // esto imprime "
```
{{% /notice %}}