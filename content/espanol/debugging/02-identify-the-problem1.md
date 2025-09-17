---
title: "Step 1 - Finding the problem (Part 1)"
difficulty: "Intermediate"
weight: 3
draft: false
---

## Compiler Errors

Comencemos y veamos uno de los primeros problemas intimidantes que enfrenta un programador novato: **leer** y **entender** los errores.

Hay dos tipos de errores: **de compilación** y **de tiempo de ejecución**.

Un error de **compilador** suele indicar un problema con tu sintaxis. Tal vez querías expresar una idea en el programa pero no respetaste las reglas del lenguaje de programación. Estos se detectan cuando compilas tu programa. Los errores de compilador son agradables porque son relativamente fáciles de arreglar. Compiladores como `gcc` normalmente dan mucha información sobre qué salió mal cuando se compiló el código. Exploremos algunos de estos errores.

Abre la pestaña **Shell** en el programa de Replit abajo y ejecuta el siguiente comando:

```bash
make CompilerErrors
```

{{% notice note %}}
Para este ejemplo, no vamos a ejecutar el programa: este programa está pensado para mostrar algunos errores comunes de compilación que podrías encontrar.
{{% /notice %}}

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Samples-C" target="_blank">Abrir Replit</a>

El primer error debería verse así (o similar):

![Error 1: Missing Semicolon](../resources/w2-01.png "A screenshot of a compiler error that says 'error: expected ';' after top level declarator'")

Notarás que el error contiene:

- el nombre del archivo que intentamos compilar (**`CompilerErrors.c`**).
- la línea donde se encontró el error (**`12`**).
- la posición en la línea donde se localiza el error (**`19`**).

Como puedes ver, el compilador te da la línea de código y apunta a dónde ocurrió realmente el error. Luego da un nombre breve del error: en este caso, el compilador esperaba un punto y coma (**`;`**) al final de la línea. Simplemente puedes añadir un punto y coma para corregir este error.

El otro error menciona que falta una llave de cierre (**`}`**) cuando no la esperaba. La solución para este también es relativamente simple: puedes añadir la llave correspondiente `{` junto a `func()`.

{{% notice warning %}}
Una llave faltante suele ser la causa de errores que parecen extraordinarios. El compilador no es muy bueno detectando dónde debería ir una llave, así que si incluyes un archivo de cabecera con una llave faltante, explotará en tu cara. En casi todos los casos, cuando el compilador muestra una serie de errores en código que no escribiste, hay muchas probabilidades de que falte una llave en alguna parte de tu código (¡o quizás incluso en el código de la librería!).
{{% /notice %}}

Una vez que lo hayas arreglado, puedes compilar el código de nuevo usando el mismo comando.

```bash
make CompilerErrors
```

Espera, ¡hay más errores! Como se mencionó en la caja de advertencia, el compilador no es muy bueno localizando errores si falta una llave. Un error de compilación puede "ocultar" a otros.

Usaremos una tabla para mostrar errores comunes de compilación y su causa general.

| Error | Causa | Solución general |
|---|---|---|
| Missing semicolon | Falta un punto y coma. | Añade el punto y coma `;`. |
| Expected function body after function declarator | Falta una llave `{`, normalmente al inicio del cuerpo de una función. | Añade la llave `{` donde corresponda. |
| Expected identifier or '('| En el contexto de una llave, normalmente significa que tienes una llave extra `{` colgando. | Elimina la llave o añade la correspondiente `}` después de ella. |
| Redefinition of ... | En algún lugar de tu código declaraste una variable. Más adelante la volviste a declarar. | Renombra las variables o elimina una de las declaraciones. |
| Use of undeclared type... | El compilador no puede encontrar la declaración de un tipo que quieres usar. | Usualmente esto proviene de directivas `#include` incorrectas (los tipos suelen declararse en archivos de cabecera). Asegúrate de que no haya errores tipográficos. |
| Must use `struct` (or `enum`) tag | C requiere que uses `struct NOMBRE_DEL_TIPO` o `enum NOMBRE_DEL_ENUM` cuando quieres referirte al tipo struct/enum. | Normalmente los desarrolladores en C usan `typedef` para no tener que escribir `struct` o `enum` al referirse a esos tipos. También puedes añadir esas palabras clave tú mismo. |
| No member named... | En tu `struct` no existe un campo con el nombre que solicitas. | Probablemente un error tipográfico, o no has definido todavía ese campo en tu `struct`. |
| Incompatible types... | Estás mezclando tipos, lo cual no está permitido en C sin un cast explícito. | Revisa si una asignación es correcta, o usa un cast explícito para silenciar el error en tiempo de compilación. Esto podría llevar a errores en tiempo de ejecución. |
| Argument type is incomplete | Si una función devuelve void, ¡no puedes pasarla como argumento a otra función! | Corrige la declaración de la función para que no sea void, y asegúrate de que realmente deseas ese comportamiento. |
| Extraneous '(' or ')' before ';' | Paréntesis desparejados `()` | Tienes un par extra de paréntesis en alguna parte. Revisa que cada par tenga su correspondiente pareja. |

Si aplicar una solución general no funciona, entonces debes recurrir a Internet para pedir ayuda. Para errores comunes con soluciones simples, saber leer el error y descifrar lo que pide arreglar puede ser mucho más rápido que buscarlo en la red.

{{% notice warning %}}
No todos los compiladores proporcionan información útil. Por ejemplo, los errores de compilación en C++ pueden ir desde simples (como en `CompilerErrors.c`) hasta enormes bloques de texto, especialmente al trabajar con plantillas (templates). El objetivo de esta lección NO es alejarte completamente de las fuentes en Internet, sino familiarizarte lo suficiente con los errores para que tengas intuición sobre cómo arreglar errores simples.
{{% /notice %}}