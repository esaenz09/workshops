---
title: "Printing to Console"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 4
---
A veces el juego o la aplicación puede no funcionar como esperas o quieres escribir algo en la consola con fines de registro. Además de depurar la aplicación, puedes usar `System.out.println()` para escribir tu mensaje. Busca tus mensajes en la ventana "logcat" en la parte inferior de Android Studio:
<img src="../resources/_gen/images/println.gif" height="60%" width="60%" title="System.out.println()" alt="Logcat window in Android Studio showing messages created using the System.out.printIn logging function"/>

{{% notice tip %}}

## Trabajando juntos

1. Sin quitar las comillas, intenta cambiar `"Restarting the Tac-Tic-Toe Game!"` por `"Restarting the Tic-Tac-Toe Game!"` o por cualquier otra frase que prefieras. Pulsa ejecutar para ver si cambia algo.
2. Añade otra línea con `System.out.println` debajo de la línea actual para imprimir una segunda frase debajo de la primera.
3. Pulsa ejecutar para ver si se imprimen dos frases. Si ves texto rojo, pide ayuda.

{{% /notice %}}

{{% notice warning %}}
## ¡AYUDA! ¡Tengo mucho texto rojo!

Si ves texto en rojo, ¡has encontrado algunos errores! Por favor pide ayuda. Ten en cuenta lo siguiente cuando programes en Android:

1. `out` y `println` comienzan con letra minúscula.
2. `System` comienza con letra mayúscula.
3. Asegúrate de que la frase que quieres imprimir esté entre comillas y que la frase esté dentro de los paréntesis.
4. No elimines ninguna llave `{` o `}`.

{{% /notice %}}

`System.out.println` es útil cuando quieres arreglar errores en el código, pero tu usuario (la persona que usa la app) no puede ver el texto impreso con esta función. ¡Pero podemos mostrar texto al usuario con toasts! Un toast es un texto breve y pequeño que hacemos visible para el usuario. Así es como se crea un toast:
```kotlin
Toast.makeText(this, "Text we want to show", Toast.LENGTH_SHORT).show()
```
<img src="../resources/_gen/images/toast_example.png" title="Toast Example" alt="toast example. You can use the toast.makeText function with arguments context, the message string, and Toast.LENGTH_LONG or Toast.LENGTH_SHORT to display a welcome message, such as Welcome to Tic-Tac-Toe"/>