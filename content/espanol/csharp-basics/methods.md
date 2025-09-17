---
title: "Methods"
description: "Introduce methods in C#."
date: 2024-09-16T00:00:00Z
weight: 7
---

## ¿Qué es un método?

Hasta ahora hemos aprendido cómo almacenar datos en variables, imprimir datos y oraciones, y tomar decisiones con sentencias `if`, bucles `for` y bucles `while`.

En el ejercicio anterior, sabemos que el siguiente bloque de código calcula la suma de 1 a 100:

```C#
int total = 0;
int num = 1;
while(num <= 100){
    total = total + num;
    num = num + 1;
}
Console.WriteLine("Sum: " + total);
```

¿Pero qué pasa si queremos calcular la suma de 1 a 77 en su lugar? ¿Cómo lo hacemos sin volver a escribir todo el bloque de código?

Queremos crear una ✨ caja mágica ✨ en el código que haga el cálculo por nosotros sin importar qué 2 números queramos sumar.
<img src="../images/method.png" height="250" alt="Num 1 and Num 2 with arrow pointing into a circle with the words Magic Box and an arrow pointing out of the circle pointing to Sum of Num 1 to Num 2"/> 

En C#, un **método** es como la caja mágica que realiza una tarea específica ejecutando un bloque de código que puede usar entradas del usuario.

Un método tiene 2 partes: firma y cuerpo:

{{% notice note %}}
### Firma del método

Para definir un método, primero necesitamos escribir su <b>firma del método</b>. Una cabecera de firma tiene cuatro partes principales:

```
access_specifier return_type method_name(list_of_parameters)
```

**Nombre de la parte** | **Descripción** | **Ejemplos u opciones posibles**
----|----|----
**especificador de acceso** | proporciona el nivel de acceso al método | `public` indica que cualquiera puede usar este método. `private` indica que solo puede llamarse dentro de una clase. (¡Aprenderemos sobre clases en la siguiente página!) `protected` indica que puede llamarse por objetos de la misma clase o derivadas.
**tipo de retorno** | tipo de dato que se devuelve a la función que llamó; técnicamente el tipo de retorno no es parte de la firma en C# | `string` o `int`, usa `void` si el método no devuelve nada.
**nombre del método** | nombre del método, usado para llamarlo | un nombre descriptivo que elijas según lo que haga el método.
**lista de parámetros** | lista de entradas que deben proporcionarse cuando se usa el método | puede tener cero o más parámetros en la forma (`tipo` `nombreParametro`, `tipo` `nombreParametro`, ... ). Usa () para sin parámetros.

```
// un ejemplo que toma un string como parámetro y devuelve otro string en respuesta
public string artist (string songName)
```
Nota: Los nombres de las variables para los parámetros no tienen que coincidir con el nombre de la variable de los datos que se pasan al método.

### Cuerpo del método

A continuación, ponemos el bloque de código asociado con el método en el **cuerpo del método**, que va entre `{` y `}` después de la firma del método.

Para devolver algún dato, usamos la palabra clave `return` seguida de una variable o un valor a devolver.

Nota: Una vez que usas `return`, nada de lo que esté después en el método se ejecuta.

Este es un ejemplo de cómo definir un método que devuelve la suma de números desde `numA` hasta `numB`:

```c#
/* Nombre del método: sumNum
 * Entrada/Parámetro: 2 números de tipo int
 * Funcionalidad: devuelve la suma desde numA hasta numB
 */
public int sumNum(int numA, int numB){
    int total = 0;
    int num = numA;      // accedemos al primer parámetro con el nombre numA
    while(num <= numB){  // accedemos al segundo parámetro con el nombre numB
        total = total + num;
        num = num + 1;
    }
    return total; // instrucción return
}
```

### Llamada al método

Por último, para ejecutar un método en tu código, necesitamos hacer una **llamada al método**. Escribimos el nombre del método con las entradas apropiadas. 
Por ejemplo:

```C#
sumNum(1, 3); // una línea de código que llama al método sumNum() con el valor de retorno 6
```

Sabiendo que `sumNum(1, 3)` devuelve un `int` con la suma de 1 a 3, podemos hacer lo siguiente para almacenar y luego imprimir el valor:

Para llamar a este método podrías hacer esto
```c#
    int sum = 0;
    sum = sumNum(1, 3);
    Console.WrlineLine(sum); // imprime 6
```

Una de las razones por las que los métodos son poderosos es que podemos llamarlos más de una vez:
```C#
    int sum = 0;
    sum = sumNum(1, 3);
    Console.WrlineLine(sum); // imprime 6
    sum = sumNum(1, 4);
    Console.WrlineLine(sum); // imprime 10
```

También podríamos haber escrito lo anterior para simplemente imprimir los números devueltos sin almacenarlos en una variable:
```c#
    Console.WriteLine(sumNum(1,3)); // imprime 6
    Console.WriteLine(sumNum(1,4)); // imprime 10
```
{{% /notice %}}

## ¡Cuenta la Pirámide!🔺

Aquí hay una imagen de una pirámide de números cuadrados donde cada nivel es el cuadrado perfecto del número del nivel contando desde la cima.

<img src="../images/pyramid.png" height="250" alt="pyramid with layers of colorful beads. Bottom layer is yellow, next blue, next brown, next white, next pink, next light blue, next orange, next coral, next green, last red" /> 

El nivel superior tiene `1 * 1` cuenta, el segundo nivel tiene `2 * 2` cuentas, y así sucesivamente.

¡Escribamos un método que tome el número de niveles totales y devuelva el número total de cuentas en la pirámide!

Una vez que resuelvas el desafío, verás el siguiente mensaje:

```
¡Felicidades! ¡Desafío resuelto!
```

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/ireaAA" frameborder="0"></iframe>