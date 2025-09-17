---
title: "1. Set Up the Board!"
description: "Using print statements prompt the game rules and board"
date: 2021-10-14T00:00:00Z
weight: 2
---

En esta actividad, tendremos un programa que imprime el tablero del juego y el aviso de juego, como en la salida siguiente:

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 2
 O | X |   
---+---+---
   |   |   
---+---+---
   |   |   
Enter your move (1-9): 
```

## The Main Class and Main Method

Fíjate que en el código inicial tenemos la clase `Main` y el método `main()`. El método `main()` es donde comienza el programa cuando hacemos clic en el botón `Run`.

```java
public class Main {
  public static void main(String[] args) {
  }
}
```

## Print Statements

En `main()`, escribe sentencias de impresión (print) para mostrar la declaración de bienvenida y las reglas del juego:

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'
```

## Variables and Arrays

En este juego, ten en cuenta que tendremos que llevar el seguimiento del símbolo que hay actualmente en cada una de las 9 posiciones del tablero.

Por lo tanto, necesitaremos almacenar 9 piezas de datos en el programa. Usemos un `array` (una estructura de datos) de tamaño 9 para guardarlos.

Como se indica en las reglas, en el tablero `"X"` es la jugada del jugador, `"O"` es la jugada de la computadora, y `" "` es un espacio disponible.

Para esto, declara una variable de tipo arreglo llamada `board` con el valor `" "` (String) en las 9 posiciones (es decir `{" ", " ", " ", " ", " ", " ", " ", " ", " "}`).

## Displaying the board

Ahora que tenemos la variable `board` que almacena los símbolos actuales en el tablero, intentemos imprimir un tablero vacío usando sentencias de impresión (como se muestra abajo).

Ten en cuenta que cada tablero consta de 5 líneas, por lo que es razonable tener 5 sentencias `print` para imprimir cada línea del tablero.

Cada uno de los 9 bloques es un `String` de longitud 3, donde el carácter del medio es el símbolo actual almacenado en `board` en la posición correspondiente.

Deberías tener un programa que produzca la siguiente salida después de completar este paso.

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

   |   |  
---+---+---
   |   |  
---+---+---
   |   | 
```

## Methods

Como sabemos que necesitaremos imprimir el tablero actual varias veces durante el juego, será buena idea mover el bloque de código que escribiste en el paso anterior a un método.

Este método debe recibir como entrada un `String[]` y debe imprimir el tablero actual. Ten en cuenta que este método debe estar escrito fuera de `main()`.

Escribamos un método con la siguiente cabecera:

```java
public static void printBoard(String[] curBoard);
```

## Calling Methods

En `main()`, llama a `printBoard()` para que imprima el tablero inicial con las posiciones numeradas. Puedes hacer esto creando otro `String[]` con el contenido `"1", "2", ..., "9"`.

Incluye una línea de código que imprima `Enter your move (1-9): `

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 
```

## Run the Program

Ejecuta tu programa; si produce el texto de arriba, ¡estás listo para continuar!