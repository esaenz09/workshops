---
title: "Step 1 - Finding the problem (Part 3)"
difficulty: "Intermediate"
weight: 5
draft: false
---

## Depuradores

Depurar código es un problema tan extendido y común que la gente ha creado programas enteros diseñados para ayudar a otros programadores a depurar de forma más eficiente. Estos se llaman **depuradores**, y hay muchos depuradores que funcionan con el lenguaje de programación C. Veamos `gdb`, un depurador común usado desde la línea de comandos.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Samples-C" target="_blank">Launch Replit</a>

Para nuestros ejemplos, usaremos el algoritmo de <a href="https://www.youtube.com/watch?v=SLauY6PpjW4" target="_blank">Quicksort</a>.

**Quicksort** es un algoritmo que ordena un arreglo seleccionando primero un elemento del arreglo como `pivot`.

A continuación, los elementos se organizan según una de las siguientes condiciones:
- Elementos menores que el pivot.
- Elementos mayores que el pivot.

Cuando se completa la ordenación, el mismo proceso se llama recursivamente en las particiones superior e inferior del arreglo, tomando el pivot como punto medio.

{{% notice note %}}
Nuestra versión de quicksort asume que el elemento más a la izquierda es el elemento "mayor" y que el elemento más a la derecha es el pivot dentro de la partición.
{{% /notice %}}

|![Quicksort using pivot as the rightmost element.](../resources/debugging_process_quicksort.svg "Multi-step process of quicksort using pivot as the rightmost element.")|
|:--:|
|Figura 1: Quicksort usando el elemento más a la derecha como pivot y asumiendo que el elemento más a la izquierda es el elemento "mayor".|

[GDB (GNU Project Debugger)](https://sourceware.org/gdb/) es un depurador potente que te permite depurar programas desde la línea de comandos, lo cual es útil en casos donde no tienes acceso a una GUI (Interfaz Gráfica de Usuario).

Es importante entender cómo funciona el programa para realizar una depuración eficaz. Nuestra implementación de 'quicksort' ejecuta una versión recursiva de quicksort y realiza la ordenación si el elemento actual es menor que el pivot, asumiendo que el primer elemento es el elemento "mayor". La ordenación en sí ocurre en la función `partition`.

### Pasos para depurar con GDB
#### Compilar el programa
1. Abre la pestaña **Shell** y compila el programa:

```bash
make Quicksort
```

{{% notice note %}}
Cuando se compila el programa, se usan las banderas: `-g` y `-Og`. La primera indica al compilador que añada **información de depuración**, lo que significa que sin esa bandera gdb no podría depurar el programa. La segunda indica al compilador que optimice el programa de una manera que no afecte la estructura de ejecución del programa. Sin `-Og`, el compilador podría optimizar y eliminar parte de tu código, por lo que un depurador no sería tan efectivo.

Es importante tener en cuenta la segunda bandera. Para depurar, **SIEMPRE** debes asegurarte de que el compilador haga optimizaciones mínimas en tu código porque las optimizaciones podrían cambiar drásticamente cómo se ejecuta el código.
{{% /notice %}}

#### Ejecutar el programa 
1. Escribe el comando `gdb examples/Quicksort`. Esto abrirá la interfaz de línea de comandos de GDB. Para depurar un programa con `gdb` puedes usar `gdb <name of program>`.

2. Asegúrate de que GDB diga que está `Reading symbols from ./examples/Quicksort...`, de lo contrario no adjuntaste el programa a GDB. 

3. Puedes salir de GDB introduciendo el comando `quit` (o cualquiera de sus prefijos: `q` funciona) como si fuera el comando normal de la shell.

Deberías ver algo como esto:

|![Running GDB on 'Quicksort' file.](../resources/w4-01.png "Screenshot of the console after running GBD on the 'Quicksort' file.")|
|:--:|
|Figura 2: Ejecutando GDB sobre el archivo 'Quicksort'.|

#### Depurar el programa

Para depurar el programa, necesitamos ejecutarlo desde GDB. 

1. Introduce el comando `run` (o `r`). Esto ejecutará el programa como si lo hubieras corrido desde la línea de comandos normal.
```bash
(gdb) run
```

El programa primero imprime el contenido del arreglo a ordenar: un arreglo de números desordenados. A continuación, ejecuta el algoritmo de ordenación y, finalmente, imprime el arreglo ordenado. ¡Puedes ver cómo el arreglo se desplaza durante la ordenación!

Sin embargo, parece que la ordenación no está ocurriendo como se esperaba.

Usemos una de las herramientas más importantes que ofrecen los depuradores: los **breakpoints** (puntos de interrupción). Un breakpoint le dice al depurador que pause el programa cada vez que alcanza esa línea de código mientras se está ejecutando. Esto te permite observar lo que está ocurriendo dentro del programa en tiempo real. Ten en cuenta que el depurador no ejecuta la línea de código en la que está el breakpoint hasta que continúas la ejecución del programa.

Primero identifiquemos dónde ocurre toda la ordenación de los elementos. ¿Sabes dónde está ocurriendo la ordenación?
{{% expand "***Answer***" %}}
La ordenación ocurre dentro del bucle `for` y al final del proceso cuando el pivot se intercambia con el elemento "mayor".
{{% /expand %}}
<br/>

2. Coloca un breakpoint donde ocurre la ordenación usando la sintaxis `break <filename:line>`.
{{% expand "***Answer***" %}}
```bash
(gdb) break quicksort.c:27
``` 
{{% /expand %}}
<br/>

3. Ejecuta el programa con `run` y observa cómo el programa se detiene cuando alcanza el breakpoint. 

4. Mientras el programa está pausado, puedes ver los valores de las variables. Prueba algunas instrucciones `print` para evaluar expresiones. Aquí tienes un ejemplo de cómo usar declaraciones print:
```bash
# puedes imprimir el valor de una variable
print myVariable

# puedes crear declaraciones print más elaboradas usando expresiones completas
print myVariable + 2 
```

5. Puedes avanzar manualmente por tu código usando `next` (o `n`), lo que le dice al depurador que avance a la siguiente línea de código **sin entrar en una llamada a función**. 

6. El comando `step` moverá el depurador a la primera línea de código dentro de una llamada a función.

Necesitas encontrar las variables defectuosas que hacen que tu programa no funcione como se espera. ¡Intenta ver si puedes localizar el problema!

{{% expand "***Hint: Keep an eye on how the variables in the loop change.***" %}}
Como colocamos el breakpoint dentro del bucle, en cada iteración deberíamos ver los valores `p1` y `p2` cambiar.

Prueba a imprimir estas variables cada vez que el depurador detenga tu código.

```bash
(gdb) disp p1
(gdb) disp p2
```
{{% /expand %}}
{{% expand "***Answer***" %}}
La variable `p1` no se está incrementando cuando se encuentra un número menor que el pivot. Recuerda que en nuestra versión se asumirá que cada vez que se encuentra un elemento menor, el puntero para el elemento mayor debe actualizarse.

Agrega `p1++;` después de la instrucción `swap` en la línea 27.

|![Fixing our quicksort algorithm.](../resources/debugging_process_fixing_quicksort.svg "Screenshot of code where 'p1++;' is created after line 27")|
|:--:|
|Figura 3: Corrigiendo nuestro algoritmo quicksort.|

{{% /expand %}}
<br/>

Ten en cuenta que todos los depuradores deberían compartir los mismos conceptos básicos: te permiten avanzar por tu código mientras se ejecuta, en tiempo real. Casi siempre deberías usar depuradores en lugar de declaraciones print. ¡No te arrepentirás!

### Comandos de GDB
GDB ofrece muchos comandos. Esta tabla resume algunos útiles, pero también recomendamos usar esta [GDB Reference Sheet](https://cs.brown.edu/courses/cs033/docs/guides/gdb.pdf) para ver más comandos que puedes usar.

| Command | Qué hace |
|---|---|
| `gdb <name of program>` | Ejecuta/carga el programa con GDB |
| `run` or `r` | Ejecuta el programa ejecutable cargado |
| `quit` or `q` | Sale de GDB |
| `break <filename:line>` | Crea un punto de interrupción en el archivo y número de línea especificados |
| `print <variable name>` or `print <expression>` | Imprime el valor de una expresión que puede contener nombres de variables y constantes |
| `next` or `n` | Avanza a la siguiente línea de código sin entrar en una llamada a función |
| `step` | Se mueve a la primera línea de código dentro de una llamada a función | 
| `continue` or `c` | Continúa ejecutando el código hasta el siguiente breakpoint | 
| `delete <breakpoint #>` or `d <breakpoint #>` | Elimina un breakpoint con el número # |
| `backtrace` or `bt` | Imprime un rastro de pila, o qué funciones fueron llamadas para llegar a la línea de código en la que el programa está detenido |