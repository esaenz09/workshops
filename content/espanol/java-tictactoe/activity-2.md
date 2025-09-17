---
title: "2. Read and Process Input"
description: "Read input with Scanner class and check error cases"
date: 2021-10-14T00:00:00Z
prereq: "Set up the Board!"
difficulty: "Intermediate"
weight: 3
draft: false
---

## Importing Packages

En Java, una forma eficiente de obtener la entrada del usuario es usar la clase `Scanner` del paquete `java.util`. Para usar esta clase y todos sus métodos, necesitamos `importar` la clase con la siguiente línea de código al inicio del archivo.

```java
import java.util.Scanner;
```

## Using the Scanner Class

En `main()`, primero necesitamos crear un objeto `Scanner` llamado `sc` llamando a su constructor (se muestra abajo).

Queremos que `Scanner` lea nuestra entrada desde el flujo de entrada estándar. Para eso debemos pasar `System.in` (el objeto del flujo de entrada estándar).

```java
// Crear un objeto Scanner
Scanner sc = new Scanner(System.in);
```

## Obtaining User Input

En la actividad anterior, pedimos al usuario que introduzca números del 1 al 9. Por lo tanto, esperaremos un `int` desde el flujo de entrada.

Para obtener el `int` que el objeto `Scanner` almacena, llamamos al método `nextInt()` sobre `sc`, el objeto `Scanner`.

```java
int input = sc.nextInt();
```

## Test Your Program (optional)

Para probar tu programa, añade una instrucción de impresión para mostrar el valor que guardas desde `nextInt()`.

Intenta ejecutar tu programa, escribe algunos números y pulsa `enter`. Deberías ver tu número impreso correctamente. Por ejemplo:

```
<<<~  Tic  Tac  Toe  ~>>>
* Choose number 1 - 9 to place your move
* Player: 'X' Computer: 'O'

 1 | 2 | 3 
---+---+---
 4 | 5 | 6 
---+---+---
 7 | 8 | 9 
Enter your move (1-9): 2                 <------- the number you typed in
Input Number: 2                          <------- Print statement printed the inputted number correctly
```

{{% notice warning %}}
#### ¿Qué pasa cuando el usuario escribe algo que no es un número?

Al escribir programas, nunca podemos esperar que los usuarios introduzcan los valores correctos aunque estén indicados en el mensaje.

Dado que nuestro programa solo espera una entrada `int`, el programa fallará cuando escribas cualquier cosa que no sea un entero, como: `hi`, `$`, `20.1`. Verás un mensaje de error similar al siguiente:

```
Exception in thread "main" java.util.InputMismatchException      <------ tells you what error it is
    at java.base/java.util.Scanner.throwFor(Scanner.java:939)
    at java.base/java.util.Scanner.next(Scanner.java:1594)
    at java.base/java.util.Scanner.nextInt(Scanner.java:2258)
    at java.base/java.util.Scanner.nextInt(Scanner.java:2212)
    at Main.main(Main.java:15)                                   <------ tells you which line of code causes the error (line 15 in Main.java)
```

Además, ten en cuenta que entradas numéricas que no estén en el rango 1 - 9 no provocarán que el programa falle, pero tampoco son entradas que deseemos.
{{% /notice %}}

## Handling Invalid Inputs with Scanner

La clase Scanner proporciona métodos que verifican entradas válidas o inválidas. Por ejemplo, el método `hasNextInt` comprobará si el valor de la entrada del usuario es un entero y devuelve `true` o `false`. Este método puede usarse para asegurar que la entrada del usuario sea válida.

Usa estructuras de control para validar la entrada del usuario. Si la entrada no es válida, solicita la entrada válida de nuevo.

```java
if(sc.hasNextInt()) { // ¿se ha introducido un entero?
	move = sc.nextInt(); // obtener la entrada entera
   if (!(move > 0 && move <= 9)) { // ¿está el entero entre 1 y 9?
		System.out.print("Invalid Position; re-enter your move (1-9): ");
   }
} else { // si no se ha introducido un entero
   sc.next(); // limpiar el Scanner
	System.out.print("Invalid Input; re-enter your move (1-9): ");
}
```

## Test Your Program (optional)

Prueba tu programa haciendo clic en `Run`, deberías ver el mensaje `Invalid Position; re-enter your move (1-9):` si ingresaste una entrada que no es un número, o un número que no esté entre 1 y 9.

## Taking Multiple Inputs

Ahora tenemos un programa que toma una entrada y evalúa si es válida; queremos pedirle al jugador que lo haga de nuevo hasta que termine el juego.

Para seguir pidiendo al usuario que introduzca su siguiente jugada, ponemos toda la sentencia `if` con `hasNextInt` dentro de un `while`. Este `while` recibe como argumento `true`, lo que significa que el programa continuará iterando hasta que se le indique que pare.

Ten en cuenta que llamamos a `printBoard(board)` y pedimos la entrada al usuario al final de cada iteración, como se muestra a continuación:

```java
while(true){
    // insert the hasNextInt() if statement here

   // move these into the hasNextInt() if statement 
    printBoard(board);
    System.out.print("Enter your move (1-9): "); 
}
```

## Handling Invalid Input

Cuando un usuario introduce una entrada inválida, no queremos que el programa llame a `printBoard(board)` ni que imprima `Enter your move (1-9): `.

En otras palabras, queremos que el programa `continue` y pase a la siguiente iteración del `while`.

Pon `continue;` en el código para indicar al ordenador que salte de nuevo y ejecute desde la parte superior del `while`.

Al final de este ejercicio, deberías tener un programa que te solicite reingresar cualquier entrada inválida e imprima un tablero vacío con el mensaje `Enter your move (1-9): ` para cualquier entrada válida.

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

¡Continuemos en el taller para ver cómo debemos actualizar nuestro tablero de juego!