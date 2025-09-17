---
title: "3. Update the Game Board"
description: "aprender a generar un movimiento para la computadora y actualizar el tablero"
date: 2021-10-14T00:00:00Z
prereq: "Set up the Board!, Read and Process Input"
difficulty: "Intermediate"
weight: 4
---

En el ejercicio anterior tenemos un programa que imprime el tablero y solicita al usuario con el mensaje `Enter your move (1-9):` después de cada movimiento válido. Sin embargo, el tablero permanecía vacío (como se muestra abajo). En este ejercicio aprenderemos a actualizar el tablero y generar un movimiento aleatorio para la computadora.

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 1
   |   |   
---+---+---
   |   |                                    <--------------- The board doesn't have the player/computer moves
---+---+---
   |   |   
Enter your move (1-9): d
Invalid Input; re-enter your move (1-9): 3
   |   |   
---+---+---
   |   |                                    <--------------- The board doesn't have the player/computer moves
---+---+---
   |   |   
Enter your move (1-9): 
```

## Mostrar los movimientos del usuario

Dentro de la sentencia `hasNextInt()` y antes de la llamada al método `printBoard(board)`, actualiza el arreglo `board` con la entrada del usuario en el índice correspondiente.

Ten en cuenta que el jugador está representado por `"X"` en el tablero.

{{% notice tip %}}
### Recordatorios

- Java usa indexación desde 0 y al jugador se le pidió que ingrese un número del 1 al 9.
- Para acceder a un elemento de un arreglo se usa la notación de índice: `myVariable[indexNumber]`.
{{% /notice %}}

## Preparar los movimientos de la computadora

Crea un nuevo método `getComputerMove(String[] curBoard)` que produzca un movimiento válido para la computadora (entre 1 y 9) recibiendo como entrada el tablero actual.

Sigue los pasos siguientes para implementar el método.

## Implementando el movimiento de la computadora

En `getComputerMove()`, generaremos aleatoriamente un número entre 1 y 9 para la computadora.

Lo haremos con la ayuda de la clase `Random`, que se usa con frecuencia en Java para generar números aleatorios.

Para usar esta clase y todos sus métodos, necesitamos importar la clase con la siguiente línea de código al inicio del archivo.

```java
import java.util.Random;
```

Crea un objeto `Random` llamando al constructor `Random()`.

```java
Random rand = new Random();
```

## Generar números aleatorios

Llama al método `int nextInt(int num)` sobre el objeto `Random` que creaste para generar un número aleatorio de 1 a 9.

Una llamada al método `int nextInt(int num)` devolverá un número aleatorio desde 0 hasta `num-1`.

```java
int position = rand.nextInt(9);
```

## Comprobar si el movimiento es válido

Después de obtener un número aleatorio entre 1 y 9, debemos comprobar si la casilla está disponible.

Usa un bucle `while` para generar un movimiento válido para la computadora si el número generado anteriormente no corresponde a una casilla disponible.

Devuelve el número una vez que encontremos un movimiento válido para la computadora.

```java
while (!curBoard[position].equals(" ")){
   position = rand.nextInt(9);
}
return position;
```

## Actualizar el arreglo del tablero

Al igual que en el primer paso, debemos actualizar el arreglo `board` para la computadora antes de la llamada al método `printBoard(board)`.

Genera aleatoriamente un movimiento llamando a `getComputerMove()`.

Ten en cuenta que la computadora está representada por `"O"` en el tablero.

```java
board[getComputerMove(board)] = "O"; //getComputerMove returns the integer 0-8 that is the proper position in the array
printBoard(board);
```

## Ejecutar el programa

¡Ejecuta el programa ahora! El tablero debería actualizarse correctamente con los movimientos del jugador y de la computadora tras cada entrada, como se muestra a continuación:

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 1
 X |   |   
---+---+---
   |   |   
---+---+---
   | O |   
Enter your move (1-9): 1
Invalid Position; re-enter your move (1-9): 2
 X | X |   
---+---+---
   |   | O 
---+---+---
   | O |   
Enter your move (1-9): 
```

¡Todo parece funcionar bien! Solo nos falta determinar quién gana o pierde la partida, lo que implementaremos en el siguiente ejercicio.