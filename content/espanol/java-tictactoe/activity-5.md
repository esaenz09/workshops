---
title: "5. (Optional) AI Move"
description: "Usa el algoritmo Minimax para elegir el movimiento de la computadora"
date: 2021-10-14T00:00:00Z
weight: 6
prereq: "Configura el tablero!, Lee y procesa la entrada, Actualiza el tablero del juego, Comprueba el ganador"
difficulty: "Avanzado"
---

### Hagamos que la computadora piense

Anteriormente usamos un objeto `Random` para generar aleatoriamente un movimiento para la computadora. Como resultado, la competitividad de la computadora es bastante baja.

En este ejercicio queremos aumentar la dificultad del juego tomando decisiones óptimas para la computadora.

Lo haremos añadiendo inteligencia artificial a nuestro programa mediante el uso del algoritmo **Minimax** (un procedimiento bien definido que permite a las computadoras resolver problemas).

### Algoritmo Minimax

Minimax es un algoritmo que se usa en juegos de dos jugadores para tomar decisiones óptimas para un jugador.

- Los dos jugadores se etiquetan como <b>maximizador</b> y <b>minimizador</b> respectivamente. Mientras el maximizador maximiza su probabilidad de ganar, el minimizador intenta minimizar su pérdida.
- El algoritmo examina todos los posibles estados futuros del juego a partir del tablero actual asumiendo que tanto el maximizador como el minimizador escogerán el movimiento que más les beneficie.
- En nuestro caso, elegimos que la computadora sea el maximizador, y el jugador el minimizador. ¡Intentaremos tomar decisiones óptimas para la computadora maximizando su probabilidad de ganar!

### ¿Cómo funcionará Minimax en TicTacToe?

- Examinamos todos los posibles movimientos de `"X"` y `"O"` y damos una puntuación a un tablero si hay un ganador o empate.
- Puesto que queremos que la computadora gane con el menor número de pasos posible, diseñamos la puntuación para los tableros de la siguiente manera:

- Si la computadora gana, calcula la puntuación con la fórmula `1 * (número de casillas disponibles en el tablero + 1)`.
- Si el jugador gana, calcula la puntuación con la fórmula `-1 * (número de casillas disponibles en el tablero + 1)`.
- Si hay un empate, la puntuación es `0`.
- Ten en cuenta que dando puntuaciones mayores a los estados de juego en los que la computadora puede ganar en menos pasos, estamos enseñando a nuestro código a elegir el movimiento óptimo para la computadora.

Veamos un ejemplo abajo:

<img src="../images/minimax.png" height="500" alt="example of possible options for winning tic-tac-toe as desribed in the text below." /> 

1. En la primera fila, consideramos los 3 movimientos posibles para la computadora `"O"`, que es el maximizador.
2. Examinamos todos los estados del juego hasta que todos los movimientos terminan en una victoria de la computadora, victoria del jugador o empate. Luego les asignamos su puntuación correspondiente.

    Por ejemplo, en el segundo tablero de la fila 1, la computadora gana colocando `"O"` en la posición 8. Ese estado recibirá una puntuación de `1 * (número de casillas disponibles en el tablero + 1)` = `1 * (2+1)` = `3`.

3. En los estados del juego que no tienen ganador ni empate, escogemos la puntuación más pequeña durante las rondas de minimización (cuando `"X"` hace un movimiento), y la puntuación más grande durante las rondas de maximización (cuando `"O"` hace un movimiento).
4. Si sigues las rondas de maximizar/minimizar en la imagen de arriba, deberías notar que el movimiento óptimo para la computadora es colocar `"O"` en la posición 8, permitiendo que la computadora gane en 1 movimiento desde el tablero inicial.

### Estructura del código

En activity-3 escribiste el método `int getComputerMove(String[] curBoard)` para generar aleatoriamente un espacio para la computadora. Escribamos otro método llamado `getComputerMoveAI(String[] curBoard)` que devuelva el movimiento óptimo para la computadora llamando al método `int minimax(String[] curBoard, boolean isMaximizing)`.

```java
int getComputerMove(String[] curBoard){
    // 1. este método llama a minimax() en todos los movimientos posibles que la computadora puede elegir
    // 2. toma el máximo entre todos ellos
    // 3. devuelve el movimiento óptimo
}
int minimax(String[] curBoard, boolean isMaximizing){
    // 1. En la ronda de maximizador, llama a minimax() en todos los movimientos posibles para la computadora, "O", y devuelve la puntuación máxima
    // 2. En la ronda de minimizador, llama a minimax() en todos los movimientos posibles para el jugador, "X", y devuelve la puntuación mínima
}
```

{{% notice note %}}

- El método `minimax()` es una <b>función recursiva</b>, lo que significa que la función se llama a sí misma dentro de su propia implementación.
- En nuestro método, `minimax()` se llama a sí mismo con diferentes tableros posibles colocando `"X"` o `"O"` en cada casilla disponible. Y el método elige ya sea la puntuación máxima o mínima dependiendo de si es una ronda de maximización.

{{% /notice %}}

### Escribe el método `getComputerMoveAI()`

1. Para cada casilla disponible en el tablero, coloca `"O"` en esa casilla y obtiene la puntuación para ese tablero llamando a `minimax()`.

{{% notice hint %}}

- Nota: debes pasar `false` para el segundo argumento ya que sería el turno del minimizador.
- Debes cambiar esa casilla de nuevo a `" "` después de obtener la puntuación, para mantener el estado original del tablero durante la siguiente iteración.
{{% /notice %}}

2. Lleva un seguimiento de la puntuación más alta y su posición correspondiente en cada iteración. Devuelve la posición con la puntuación más alta.

{{% notice hint %}}

- Ten una variable llamada `bestScore` que almacene la mejor puntuación actual y con un valor inicial de `Integer.MIN_VALUE` (valor mínimo de un entero).
- Esta es una forma útil de encontrar el valor máximo en una estructura de datos.
Por ejemplo:

```java
public int getLargestNum() {
    // el siguiente código encuentra el valor máximo en el arreglo "nums"
    int[] nums = {3, 5, -2, 10};
    int largestNum = Integer.MIN_VALUE;
    for(int i = 0; i < nums.length; i++){
        if(nums[i] > largestNum){
            largestNum = nums[i];
        }
    }
    return largestNum;
}
```

{{% /notice %}}

### Escribe el método `minimax()`

Como discutimos arriba, el método `minimax()` tiene la cabecera `int minimax(String[] curBoard, boolean isMaximizing)`.

1. Llama a `getWinner()` en el tablero para comprobar si hay un ganador. Si lo hay, devuelve la puntuación correspondiente.

    (Puntuación: la computadora gana (`1 * número de casillas disponibles en el tablero + 1`), el jugador gana (`-1 * número de casillas disponibles en el tablero + 1`), empate (`0`)).

2. Obtén la puntuación Minimax

- Si es el turno del maximizador (`"O"`), para cada casilla disponible en el tablero, coloca `"O"` en esa casilla y obtiene la puntuación para ese tablero llamando a `minimax()`.

- Si es el turno del minimizador (`"X"`), para cada casilla disponible en el tablero, coloca `"X"` en esa casilla y obtiene la puntuación para ese tablero llamando a `minimax()`.

3. Devuelve la puntuación adecuada

- Si es el turno del maximizador (`"O"`), registra la puntuación más alta y la posición correspondiente en cada iteración, y devuelve esa puntuación.
- Si es el turno del minimizador (`"X"`), registra la puntuación más baja y la posición correspondiente en cada iteración, y devuelve esa puntuación.

### Prueba tus métodos

Copia y pega tus dos métodos debajo de `main()`.

Haz clic en `Run` para probar tus métodos. Proveemos una prueba dada del ejemplo de la imagen arriba.

Puedes introducir diferentes tableros para comprobar si obtienes la salida deseada.
<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/JavaTicTacToeminimax" target="_blank">Abrir Replit</a>

{{% notice tip %}}
¡Recuerda probar tus métodos!
{{% /notice %}}

### Actualiza el programa

Después de probar los métodos, actualiza todas las llamadas al método `getComputerMove()` a `getComputerMoveAI()` en tu programa TicTacToe.

¡Esta vez debería ser mucho más difícil ganar 😀!