---
title: "Control Structures"
description: "Introduce if-else, for, and while loops in C#."
date: 2024-09-16T00:00:00Z
weight: 6
---

## Make a Decision: If-Statement

Patrick 🐥 es un pato muy educado que le gusta saludar a todos con "Good Morning", "Good Afternoon" o "Good Night" dependiendo de la hora actual.

![Sun rising rapidly over a mountain](https://media.giphy.com/media/hpWrLS1RDBd5pwkgjy/giphy.gif)
<p style="text-align: center;">(image by National Geographic: giphy.com/natgeochannel)</p>

Como aprendimos antes, podemos imprimir estas frases así:

```C#
Console.WriteLine("Good Morning");   // decir entre 0:00 - 11:59
Console.WriteLine("Good Afternoon"); // decir entre 12:00 - 19:59
Console.WriteLine("Good Night");     // decir entre 20:00 - 23:59
```

Sin embargo, también sabemos que Patrick 🐥 solo debe decidir decir una de estas frases según la hora actual.

En otras palabras, necesitamos escribir código que tome una decisión sobre qué imprimir en función de las condiciones de la situación (de forma condicional).

En C#, tomamos una decisión usando una **if statement** o una **if...else statement**. Lee las notas a continuación:

{{% notice note %}}
### If Statement

```
if(boolean expression){
    Action(s) to Take
}
```

Una **if statement** sigue la estructura mostrada arriba. Las acciones a realizar (sentencias) en el bloque solo se ejecutarán si la expresión booleana es `true`. De lo contrario, el programa saltará a la sentencia después del bloque si la expresión booleana es `false`.
### If-Else Statement

```
if(boolean expression){
    Action(s) to Take A
}else{
    Action(s) to Take B
}
```

Una **if-else statement** sigue la estructura mostrada arriba. Si la expresión booleana es `true`, el programa ejecutará las `Action(s) to Take A` dentro del bloque `if`. De lo contrario, el programa ejecutará únicamente las `Action(s) to Take B` dentro del bloque `else`.

### Example

```C#
    bool likeMusic = true;
    if(likeMusic == true) 
    {
        Console.WriteLine("I like Music");
    } 
    else 
    {
        Console.WriteLine("I don't like Music");
    }   
```

El código anterior imprimirá la línea `I like Music` porque la expresión booleana `likeMusic == true` es verdadera.
{{% /notice %}}

Volvamos al ejemplo del saludo anterior y decidamos qué debe decir Patrick: "Good Morning", "Good Afternoon" o "Good Night".

Patrick debe decir "Good Morning" entre 0:00 - 11:59, "Good Afternoon" entre 12:00 - 19:59, y "Good Night" entre 20:00 - 23:59.

1. Tenemos una variable `currentHour` que almacena la hora actual.
2. Rellena la `boolean expression A` y la `boolean expression B` correctas para completar el programa.
3. Prueba tu resultado asignando la variable `currentHour` a números del 0 al 23:

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/T6AUdh" frameborder="0"></iframe>

## Repeat It Again: For-Loop, While-Loop

En la clase de matemáticas, la profesora de Patrick 🐥 les pide a los alumnos resolver un reto matemático, y él podría necesitar algo de ayuda.

La profesora les pide encontrar la **suma de 1, 2, 3, ...., 100**. Es decir, ¿cuánto es **1 + 2 + 3 + 4 ... + 99 + 100**?

Aunque podríamos usar una calculadora, eso tomaría tiempo. Afortunadamente, en C# puedes calcular esto fácilmente en 3 líneas con la ayuda de un **for loop** o un **while loop**.

{{% notice note %}}
**For loops** y **While loops** son estructuras de control en C# que te permiten ejecutar bloques de código varias veces.

### While Loop

```
while(boolean expression){
    Action(s) to Take
}
```

`Action(s) to Take` en el bloque while se ejecutará mientras la `boolean expression` sea `true`. 

El siguiente es un ejemplo que imprime del 1 al 10:

```C#
int number = 1;
while(number <= 10){
    Console.WriteLine(number);
    number = number + 1;        // number se incrementa en 1
}
```

En el while anterior, el programa imprimirá el valor de `number` e incrementará `number`. Este paso se realizará siempre que `number <= 10`, y en este caso el bucle termina cuando `number` es 11.

**Nota:** Para los `while` loops, debes recordar incrementar la variable condicional; de lo contrario introducirás un bucle infinito en tu programa.

### For Loop

```
for(initialization; termination condition; update statement){
    Action(s) to Take
}
```

En un `for` loop, hay tres partes en el bloque de condición: `initialization`, `termination condition`, y `update statement`.

1. Al ejecutar un for loop, el programa ejecutará la parte de `initialization`. Un ejemplo es `int number = 1`.
2. Después, el programa comprueba la `termination condition`. Un ejemplo es `number <= 10`.
3. Si es `true`:
    1. ejecutar las `Action(s) to Take`
    2. ejecutar la `update statement` (un ejemplo es `number = number + 1`)
4. Repetir los pasos 2 y 3.
5. Si la `termination condition` es `false`, salir del `for` loop.

El siguiente es un ejemplo que imprime del 1 al 10:

```C#
for(int number = 1; number <= 10; number = number + 1){
    Console.WriteLine(number);
}
```

{{% /notice %}}

Después de aprender sobre `for` loops y `while` loops, ¿cómo ayudamos a Patrick 🐥 a calcular **1 + 2 + 3 + 4 ... + 99 + 100** fácilmente?

Intentémoslo con un `while` loop:

1. Tenemos una variable llamada `total` que rastrea la suma total que llevamos hasta ahora.
2. Tenemos una variable llamada `num` que rastrea el siguiente número que se agregará a `total`.
3. Escribe la `boolean expression` apropiada y escribe el while loop.

Siguiendo esos pasos obtendremos un `while` loop como este:

```C#
int total = 0;
int num = 1;
while(num <= 100){
    total = total + num;
    num = num + 1;
}
Console.WriteLine("Answer calculated in a while loop: " + total);
```

¡Prueba esto abajo haciendo clic en `Run` y escribe una versión con `for` loop que calcule lo mismo! ¡Deberías obtener la misma respuesta!

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/ySFwK0" frameborder="0"></iframe>