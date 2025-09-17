---
title: "4. Check the winner"
description: "write method to check the winner with an input board"
date: 2021-10-14T00:00:00Z
prereq: "Set up the Board!, Read and Process Input, Update the Game Board"
difficulty: "Intermediate"
weight: 5
---

## Mostrar al ganador

Escribe un método `getWinner(String[] curBoard)` que devuelva el ganador en un `String` con un `array` como entrada del tablero de juego actual.

- Si el jugador gana, devuelve `"Congratulations! \nYou won the Game :)"`.
- Si la computadora gana, devuelve `"Game Over! \nYou lost the Game :("`.
- Si hay un empate, devuelve `"It's a TIE! Try again"`.
- Si todavía no hay ganador, devuelve `""`.

Hay varias formas de escribir este método.

¡Pruébalo primero en el siguiente Replit; te dirá si tu método está escrito correctamente!
<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/JavaTicTacToegetWinner" target="_blank">Launch Replit</a>

{{% notice note %}}
#### Ideas/Sugerencias para escribir el método `getWinner()`

- Concatenar `Strings` en las 3 posiciones que forman una fila horizontal, vertical o diagonal.
- Usar `equals()` para comprobar si cada uno de los `Strings` concatenados es `"XXX"` u `"OOO"` para determinar un ganador. (Incluso puedes crear otro método que verifique si un `String` de entrada es `"XXX"` o `"OOO"`)
- Si todas las casillas del array están llenas (un `for loop` puede ser útil) y no hay ganador, el juego termina en empate.
{{% /notice %}}

## Llamar al método del ganador

En `main()`, llama al método `getWinner()` después de la línea de código donde colocas la jugada del jugador, `"X"`.

Comprueba si el juego debe continuar (cuando no hay ganador ni empate).

Si hay un ganador o un empate, imprime el tablero final y el resultado del juego. ¡Y añade la línea de código `break;`, que indica al programa salir del bucle `while`!

## Repite el paso anterior

En `main()`, repite el código del paso anterior (comprueba el ganador e imprime el resultado si es necesario) después de que coloques la jugada de la computadora, `"O"`.

## Cerrar el objeto Scanner

Fuera del bucle while, añade el código `sc.close()` para cerrar el objeto `Scanner` y dejar de leer nuevos inputs.

¡Es buena práctica cerrar el objeto `Scanner` si no vamos a recibir más entradas después de hacer `break` en el bucle `while`!

## ¡Todo listo :)!

¡Ahora deberías tener un juego de TicTacToe funcionando! ¡Deberías estar muy orgulloso/a de haber terminado este taller! ¡Buen trabajo 👍!

##### Como resumen, esta debería ser la estructura de tu código:
<img src="../images/code.png" height="500" alt="Tic Tac Toe: Your Java Project. void main(String args[]) that reads in player inputs, process inputs, and prompt each round of the game or print the winner of the game. void printBoard(String[] curBoard) is a method to print the game board. int getComputerMove(String[] curBoard) randomly returns an available move for the computer. String getWinner(String[] curBoard) returns the winner of the game/TIE or '' if the game should continue."/>