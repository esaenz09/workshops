---
title: "Problem 1: Tree Basics"
date: 2022-08-06T13:24:17-07:00
draft: false
weight: 3
--- 

## Tarea 1: Encontrar un valor en un árbol binario

Ahora que conocemos los conceptos básicos de cómo recorrer un árbol, implementa la búsqueda binaria basada en el proceso (o algoritmo) del que hablamos en la página anterior. Aquí tienes un breve repaso:
* Si el valor actual es menor que lo que queremos, ve al nodo derecho.
* Si el valor actual es mayor que lo que queremos, ve al nodo izquierdo.
* Si el valor actual es lo que queremos, ¡terminaste!

<iframe height="800px" width="100%" src="https://replit.com/@nuevofoundation/BinarySearch?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

{{% showanswer "SPOILER: ¡Haz clic aquí si necesitas ayuda con la solución!" %}}
```js javascript
public static Node findValue(Node root, int value) {
    // Comenzamos en la raíz del árbol
    Node current = root;

    // Seguimos la lógica que describimos arriba 
    while (current.value != value) {
        System.out.println("current value is: " + current.value);
        if (value < current.value) {
            current = current.left;
        }
        if (value > current.value) {
            current = current.right;
        }
    }

    // Si estamos aquí, ¡hemos llegado al nodo con el valor correcto!
    return current;
}
```
{{% /showanswer %}}

### ¡Felicidades! Si has llegado hasta aquí, entonces has programado oficialmente la búsqueda binaria!