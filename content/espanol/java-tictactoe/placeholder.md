---
title: "Placeholder"
date: 2020-07-23T00:00:00Z
weight: 15
draft: true
hidden: true
---

## Leer y procesar la entrada

En Java, una forma eficiente de recibir la entrada del usuario es usar la clase `Scanner` del paquete `java.util`. Para usar esta clase y todos sus métodos, necesitamos `importar` la clase con la siguiente línea de código al inicio del archivo.

```java
import java.util.Scanner;
```

## Manejo de errores

En Java, podemos tratar errores potenciales poniendo el código que pueda causar un error en un bloque `try-catch`. 

En el bloque `try`, colocamos el bloque de código que podría causar un error.

En el bloque `catch`, ponemos instrucciones sobre qué hacer si ocurre un error al ejecutar el bloque `try`. De este modo podemos evitar que el programa se caiga.
Por ejemplo:

```java
try{
   // Bloque de código a intentar
} catch(Exception e){
   // Bloque de código para manejar errores
}
```

   Ejecuta tu programa y escribe entradas que no sean números. ¡Tu programa ya no debería fallar!

## El bloque try

En el bloque `try`, obtenemos entradas numéricas de los usuarios. Sin embargo, no todas las entradas son válidas, ya que solo debemos aceptar posiciones disponibles en el tablero.

Usa sentencias if para comprobar si la entrada numérica es válida. (Pista: accede al arreglo `board` para verificar si la entrada es válida).

Si no lo es, imprime la sentencia `Invalid Position; re-enter your move (1-9):`.

{{% notice hint %}}
#### ¿Cómo compruebo si dos Strings son iguales?

Para comprobar si 2 Strings contienen el mismo contenido, llamamos al método `equals()`. Por ejemplo

```java
String s1 = "hi";
boolean b1 = s1.equals("hi"); // esto es verdadero
boolean b2 = s1.equals("HI"); // esto es falso
```

{{% /notice %}}

## El bloque catch

En el bloque `catch`, sabemos que el jugador introdujo una entrada que no es un número. Primero, necesitamos ignorar esta entrada inválida borrando esa entrada del `Scanner`. Lo hacemos llamando al método `next()` sobre el objeto `Scanner` que creamos. Después, también debemos imprimir la instrucción para informar al jugador que vuelva a introducir un movimiento: `Invalid Position; re-enter your move (1-9):`.

## (opcional) Prueba tu programa

Prueba tu programa haciendo clic en `Run`; deberías ver el mensaje `Invalid Position; re-enter your move (1-9):` si ingresaste una entrada que no es número, o un número que no esté entre 1 y 9.

## Entradas múltiples

Ahora tenemos un programa que toma una entrada y evalúa si es válida; queremos pedirle al jugador que lo haga de nuevo hasta que termine el juego.

Para seguir solicitando al usuario que introduzca su siguiente movimiento, colocamos todo el bloque `try-catch` dentro de un `while loop`. Este `while` toma como argumento `true`, lo que significa que el programa seguirá repitiendo hasta que se le indique que pare. 

Ten en cuenta que llamamos a `printBoard(board)` y solicitamos la entrada del usuario al final de cada iteración, como se muestra a continuación:

```java
while(true){
    // insert the try-catch block here

    printBoard(board);
    System.out.print("Enter your move (1-9): "); 
}
```

## Manejo de entradas inválidas

Cuando un usuario introduce una entrada inválida, no queremos que el programa llame a `printBoard(board)` ni imprima `Enter your move (1-9): `.

En otras palabras, queremos que el programa `continue` con la siguiente iteración del `while`.

Pon `continue;` en el código para indicar al ordenador que salte y ejecute de nuevo desde la parte superior del `while`.

Al final de este ejercicio, deberías tener un programa que te pida volver a introducir cualquier entrada inválida y que muestre un tablero vacío con el mensaje `Enter your move (1-9): ` para cualquier entrada válida.

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

Continuemos con el taller para ver cómo debemos actualizar nuestro tablero de juego.