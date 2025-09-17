---
title: "Operations"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 3
---

Los arreglos 2D funcionan de manera muy similar a los arreglos regulares, y muchas de las ideas o métodos que usamos en arreglos también se aplican a arreglos multidimensionales. Como recordatorio rápido, aquí se muestra cómo inicializar un arreglo 2D y acceder a un elemento:

```js javascript
public static void main(String[] args) { 
    int[][] arr = new int[10][20]; 
    arr[0][0] = 1; 
    System.out.println(arr[0][0]); 
} 
    // Imprime 1
```

La única parte que podría no tener mucho sentido al principio es iterar a través de un arreglo 2D, pero esto también es bastante sencillo. En lugar de un solo bucle `for`, usaremos dos bucles `for`. Aquí hay un ejemplo rápido para darte una idea.

```js javascript
public static void main(String[] args) { 
    int[][] arr = new int[10][20]; 
    int num = 0;

    // Iterar sobre el arreglo de arreglos
    for (int i = 0; i < arr.length; i++) {

        // Iterar sobre un arreglo individual dentro del arreglo 2D
        for (int j = 0; j < arr[i].length; j++) {

            // Acceder a valores individuales
            arr[i][j] = num;
            num++;
        }
    }
} 
```

Como puedes ver, creamos un arreglo vacío llamado `arr`. En él tenemos `10` arreglos, cada uno con `20` elementos respectivamente. Para iterar por todos los arreglos, usamos un bucle `for` estándar tal como lo haríamos con un arreglo normal. Sin embargo, la única diferencia es que ahora necesitamos crear un segundo bucle `for` que itere por el arreglo índice `i`. En este ejemplo, simplemente asignamos `arr[i][j] = num` y hacemos `num++`, manteniéndolo claro para principiantes.