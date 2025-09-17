---
title: "Java: TicTacToe - Answer Key"
date: 2020-07-23T00:00:00Z
weight: 15
draft: false
hidden: true
---

# activity-1: Configuración del juego
```java
public class TicTacToe_Nuevo {
    public static void main(String args[]){
        // el tablero que almacena los movimientos
        String[] board = {" ", " ", " ", " ", " ", " ", " ", " ", " "};
        // tablero inicial que etiqueta las posiciones (impreso solo una vez)
        String[] startBoard = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};

        System.out.println("<<<~  Tic  Tac  Toe  ~>>>\n* Choose number 1 - 9 to place your move\n* Player: 'X' Computer: 'O'\n" );
        printBoard(startBoard); 
        System.out.print("Enter your move (1-9): "); 
        }

    // método que imprime el tablero con la entrada del tablero
    public static void printBoard(String[] curBoard){
        System.out.println(" " + curBoard[0] + " | " + curBoard[1] + " | " + curBoard[2] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[3] + " | " + curBoard[4] + " | " + curBoard[5] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[6] + " | " + curBoard[7] + " | " + curBoard[8] + " ");
    }
}
```

# activity-2: Leer y procesar la entrada
```java
import java.util.Scanner;
public class TicTacToe_Nuevo {
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        /*String[] board = {" ", " ", " ", " ", " ", " ", " ", " ", " "};
        String[] startBoard = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};

        System.out.println("<<<~  Tic  Tac  Toe  ~>>>\n* Choose number 1 - 9 to place your move\n* Player: 'X' Computer: 'O'\n");
        printBoard(startBoard);
        System.out.print("Enter your move (1-9): "); */

        while(true){
            int move;
			if(sc.hasNextInt()) {
                // obtener entrada entera
				move = sc.nextInt();
                // verificar si el entero está entre 1 y 9. verificar si la posición está vacía
				if (!(move > 0 && move <= 9) || ! board[move -1].equals(" ")) {
					System.out.print("Invalid Position; re-enter your move (1-9): ");
					continue;
				}
			} else {
                // limpiar el Scanner
                sc.next();
				System.out.print("Invalid Input; re-enter your move (1-9): ");
				continue;
            }

            // volver a mostrar el tablero
            printBoard(board);
            System.out.print("Enter your move (1-9): "); 
        }
    }

    /*public static void printBoard(String[] curBoard){
        System.out.println(" " + curBoard[0] + " | " + curBoard[1] + " | " + curBoard[2] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[3] + " | " + curBoard[4] + " | " + curBoard[5] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[6] + " | " + curBoard[7] + " | " + curBoard[8] + " ");
    }*/
}
```

# activity-3: Actualizar el tablero
```java
// importar java.util.Scanner;
import java.util.Random;
public class TicTacToe_Nuevo {
    public static void main(String args[]){
        /*Scanner sc = new Scanner(System.in);
        String[] board = {" ", " ", " ", " ", " ", " ", " ", " ", " "};
        String[] startBoard = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};

        System.out.println("<<<~  Tic  Tac  Toe  ~>>>\n* Choose number 1 - 9 to place your move\n* Player: 'X' Computer: 'O'\n");
        printBoard(startBoard);
        System.out.print("Enter your move (1-9): "); */

        while(true){
            /*int move;
            if (sc.hasNextInt()) {
                move = sc.nextInt();
				if (!(move > 0 && move <= 9) || ! board[move -1].equals(" ")) {
					System.out.print("Invalid Position; re-enter your move (1-9): ");
					continue;
				}
            } else {
                sc.next();
				System.out.print("Invalid Input; re-enter your move (1-9): ");
				continue;
            }
            */

            // actualizar el tablero con el movimiento del usuario
            board[move - 1] = "X";
            
            // actualizar el tablero con un movimiento aleatorio para la computadora
            board[getComputerMove(board) - 1] = "O";

            /*printBoard(board);
            System.out.print("Enter your move (1-9): "); */s
        }
    }

    /*public static void printBoard(String[] curBoard){
        System.out.println(" " + curBoard[0] + " | " + curBoard[1] + " | " + curBoard[2] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[3] + " | " + curBoard[4] + " | " + curBoard[5] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[6] + " | " + curBoard[7] + " | " + curBoard[8] + " ");
    }*/

    // método que genera un movimiento aleatorio válido
    public static int getComputerMove(String[] curBoard){
        Random rand = new Random();
        int pos = rand.nextInt(9) + 1;
        while(! curBoard[pos - 1].equals(" ")){
            pos = rand.nextInt(9) + 1;
        }
        return pos;
    }
}
```

# activity-4: Comprobar el ganador
```java
// importar java.util.Scanner;
// importar java.util.Random;
public class TicTacToe_Nuevo {
    public static void main(String args[]){
        /*Scanner sc = new Scanner(System.in);
        String[] board = {" ", " ", " ", " ", " ", " ", " ", " ", " "};
        String[] startBoard = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};

        System.out.println("<<<~  Tic  Tac  Toe  ~>>>\n* Choose number 1 - 9 to place your move\n* Player: 'X' Computer: 'O'\n");
        printBoard(startBoard);
        System.out.print("Enter your move (1-9): "); */

        while(true){
            /*int move;
			if (sc.hasNextInt()) {
                move = sc.nextInt();
				if (!(move > 0 && move <= 9) || ! board[move -1].equals(" ")) {
					System.out.print("Invalid Position; re-enter your move (1-9): ");
					continue;
				}
            } else {
                sc.next();
				System.out.print("Invalid Input; re-enter your move (1-9): ");
				continue;
            }*/

            // board[move - 1] = "X";
            String winner = getWinner(board);
            if(winner.length() > 0){      // si hay un ganador o un empate
                printBoard(board);
                System.out.println("\n" + winner + "\n");
                break;
            }
            
            // board[getComputerMove(board) - 1] = "O";
            winner = getWinner(board);
            if(winner.length() > 0){
                printBoard(board);
                System.out.println("\n" + winner + "\n");
                break;
            }

            /*printBoard(board);
            System.out.print("Enter your move (1-9): "); */s
        }
        sc.close();  
    }

    /*public static void printBoard(String[] curBoard){
        System.out.println(" " + curBoard[0] + " | " + curBoard[1] + " | " + curBoard[2] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[3] + " | " + curBoard[4] + " | " + curBoard[5] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[6] + " | " + curBoard[7] + " | " + curBoard[8] + " ");
    }
    public static int getComputerMove(String[] curBoard){
        Random rand = new Random();
        int pos = rand.nextInt(9) + 1;
        while(! curBoard[pos - 1].equals(" ")){
            pos = rand.nextInt(9) + 1;
        }
        return pos;
    }*/
    
    // NOTA: esta es una forma posible de escribir este método. 
    public static String getWinner(String[] curBoard){
        for(int i = 0; i < 8; i++){
            String checkWin = "";
            switch(i){
                // concatenar todas las posibles posiciones ganadoras
                case 0: checkWin = curBoard[0] + curBoard[1] + curBoard[2];
                        break;
                case 1: checkWin = curBoard[3] + curBoard[4] + curBoard[5];
                        break;
                case 2: checkWin = curBoard[6] + curBoard[7] + curBoard[8];
                        break;
                case 3: checkWin = curBoard[0] + curBoard[3] + curBoard[6];
                        break;
                case 4: checkWin = curBoard[1] + curBoard[4] + curBoard[7];
                        break;
                case 5: checkWin = curBoard[2] + curBoard[5] + curBoard[8];
                        break;
                case 6: checkWin = curBoard[0] + curBoard[4] + curBoard[8];
                        break;
                case 7: checkWin = curBoard[2] + curBoard[4] + curBoard[6];
                        break;
            }
            // comprobar si algún jugador gana
            if(checkWin.equals("XXX")){
                return "Congratulations! \nYou won the Game :)";
            }else if(checkWin.equals("OOO")){
                return "Game Over! \nYou lost the Game :(";
            }
        }
        for(String move: curBoard){
            if(move.equals(" ")){
                return "";
            }
        }
        return "It's a TIE! Try again";
    }
}
```

# activity-5: Movimiento de la IA
```java
        public static int getComputerMoveAI(String[] curBoard){
            int pos = 0;
            int bestScore = Integer.MIN_VALUE;
            for(int i = 0; i < 9; i++){
                if(curBoard[i].equals(" ")){ // recorrer todas las casillas vacías
                    // colocar el movimiento de la computadora allí
                    curBoard[i] = "O";
                    // obtener la puntuación
                    int score = minimax(curBoard, false);
                    // devolverlo a su estado original
                    curBoard[i] = " ";
                    // llevar la cuenta de la posición que da la mejor puntuación
                    if(score > bestScore){
                        bestScore = score;
                        pos = i;
                    }
                }
            }
            return pos;
        }
    
        public static int minimax(String[] curBoard, boolean isMaximizing){
            // comprobar si el tablero ya tiene un ganador o un empate
            String result = getWinner(curBoard);
    
            // factor = número de casillas vacías + 1
            int factor = getFactor(curBoard);

            // estado terminal: devolver puntuación 
            if(result.contains("TIE")) return 0;
            if(result.contains("won")) return -1 * factor;
            if(result.contains("lost")) return 1 * factor;
                    
            // el código siguiente es similar a getComputerMoveAI() pero invierte según el parámetro `isMaximizing`
            int bestScore = (isMaximizing)? Integer.MIN_VALUE : Integer.MAX_VALUE;
            String symbol = (isMaximizing)? "O" : "X";
            for(int i = 0; i <9; i++){
                if(curBoard[i].equals(" ")){
                    curBoard[i] = symbol;
                    int score = minimax(curBoard, !isMaximizing);
                    curBoard[i] = " ";
                    if(isMaximizing) {
                        bestScore = Math.max(score, bestScore);
                    }else{
                        bestScore = Math.min(score, bestScore);
                    }
                }
            }
    
            return bestScore;
        }

    // devuelve el número de casillas disponibles + 1
    public static int getFactor(String[] curBoard){
        int counter = 1;
        for(int i = 0; i < 9; i++){
            if(curBoard[i].equals(" ")){
                counter++;
            }
        }
        return counter;
    }
```

# Código completo
```java
import java.util.Random;
import java.util.Scanner;

public class TicTacToe_Nuevo {
    public static void main(String args[]){
        String[] board = {" ", " ", " ", " ", " ", " ", " ", " ", " "};
        String[] startBoard = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};
        Scanner sc = new Scanner(System.in);

        System.out.println("<<<~  Tic  Tac  Toe  ~>>>\n* Choose number 1 - 9 to place your move\n* Player: 'X' Computer: 'O'\n");
        printBoard(startBoard);
        System.out.print("Enter your move (1-9): "); 

        while(true){
            int move;
			if (sc.hasNextInt()) {
                move = sc.nextInt();
				if (!(move > 0 && move <= 9) || ! board[move -1].equals(" ")) {
					System.out.print("Invalid Position; re-enter your move (1-9): ");
					continue;
				}
            } else {
                sc.next();
				System.out.print("Invalid Input; re-enter your move (1-9): ");
				continue;
            }

            board[move - 1] = "X";
            String winner = getWinner(board);
            if(winner.length() > 0){
                printBoard(board);
                System.out.println("\n" + winner + "\n");
                break;
            }

            double ran = Math.random();
            /*if(ran < 0.2){
                board[getComputerMove(board) - 1] = "O";
            }else{*/
                board[getComputerMoveAI(board) - 1] = "O";
            //}
            winner = getWinner(board);
            if(winner.length() > 0){
                printBoard(board);
                System.out.println("\n" + winner + "\n");
                break;
            }

            printBoard(board);
            System.out.print("Enter your move (1-9): "); 
        }
        sc.close();  
    }

    public static void printBoard(String[] curBoard){
        System.out.println(" " + curBoard[0] + " | " + curBoard[1] + " | " + curBoard[2] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[3] + " | " + curBoard[4] + " | " + curBoard[5] + " ");
        System.out.println("---+---+---");
        System.out.println(" " + curBoard[6] + " | " + curBoard[7] + " | " + curBoard[8] + " ");
    }
    public static String getWinner(String[] curBoard){
        for(int i = 0; i < 8; i++){
            String checkWin = "";
            switch(i){
                case 0: checkWin = curBoard[0] + curBoard[1] + curBoard[2];
                        break;
                case 1: checkWin = curBoard[3] + curBoard[4] + curBoard[5];
                        break;
                case 2: checkWin = curBoard[6] + curBoard[7] + curBoard[8];
                        break;
                case 3: checkWin = curBoard[0] + curBoard[3] + curBoard[6];
                        break;
                case 4: checkWin = curBoard[1] + curBoard[4] + curBoard[7];
                        break;
                case 5: checkWin = curBoard[2] + curBoard[5] + curBoard[8];
                        break;
                case 6: checkWin = curBoard[0] + curBoard[4] + curBoard[8];
                        break;
                case 7: checkWin = curBoard[2] + curBoard[4] + curBoard[6];
                        break;
            }
            if(checkWin.equals("XXX")){
                return "Congratulations! \nYou won the Game :)";
            }else if(checkWin.equals("OOO")){
                return "Game Over! \nYou lost the Game :(";
            }
        }
        for(String move: curBoard){
            if(move.equals(" ")){
                return "";
            }
        }
        return "It's a TIE! Try it again";
    }

    public static int getComputerMove(String[] curBoard){
        Random rand = new Random();
        int pos = rand.nextInt(9) + 1;
        while(! curBoard[pos - 1].equals(" ")){
            pos = rand.nextInt(9) + 1;
        }
        return pos;
    }

    // IA: movimiento de la computadora
    public static int getComputerMoveAI(String[] curBoard){
        int pos = 0;
        int bestScore = Integer.MIN_VALUE;
        for(int i = 0; i < 9; i++){
            if(curBoard[i].equals(" ")){
                curBoard[i] = "O";
                int score = minimax(curBoard, false);
                curBoard[i] = " ";
                if(score > bestScore){
                    bestScore = score;
                    pos = i;
                }
            }
        }
        return pos;
    }

    public static int minimax(String[] curBoard, boolean isMaximizing){
        String result = getWinner(curBoard);

        int factor = getFactor(curBoard);

        // estado terminal: devolver puntuación
        if(result.contains("TIE")) return 0;
        if(result.contains("won")) return -1 * factor;
        if(result.contains("lost")) return 1 * factor;
                
        // caso recursivo
        int bestScore = (isMaximizing)? Integer.MIN_VALUE : Integer.MAX_VALUE;
        String symbol = (isMaximizing)? "O" : "X";
        for(int i = 0; i <9; i++){
            if(curBoard[i].equals(" ")){
                curBoard[i] = symbol;
                int score = minimax(curBoard, !isMaximizing);
                curBoard[i] = " ";
                if(isMaximizing) {
                    bestScore = Math.max(score, bestScore);
                }else{
                    bestScore = Math.min(score, bestScore);
                }
            }
        }

        return bestScore;
    }

    // devuelve el número de casillas disponibles + 1
    public static int getFactor(String[] curBoard){
        int counter = 1;
        for(int i = 0; i < 9; i++){
            if(curBoard[i].equals(" ")){
                counter++;
            }
        }
        return counter;
    }
}
```