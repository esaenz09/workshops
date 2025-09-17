---
title: "Strings"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 7
---
Cualquier cosa que esté entre comillas se llama string. Así es como una computadora representa palabras o frases. Por ejemplo, `"a"`, `"2"`, `"banana!"` y `"Hello World"` son strings, pero `Hello World` y `2` no lo son, porque faltan las comillas. Puedes combinar muchos strings usando el operador `+`. Por ejemplo:

- `"Apple" + "Pineapple"` produce la string `"ApplePineapple"`.
- `"Nuevo" + " " + "Foundation"` produce la string `"Nuevo Foundation"`.

{{% notice tip %}}
## Trabajando juntos

Elimina todas tus líneas `System.out.println` de tu código. Comienza tu código con la línea `System.out.println("Nuevo" + " " + "Foundation");`. Ten en cuenta que hay muchas maneras de combinar strings. Por ejemplo, otra forma de imprimir Nuevo Foundation sería escribir `System.out.println("Nue" + "vo Fou" + "ndation");`. Vamos a idear al menos una forma más de imprimir la string `"Nuevo Foundation"` usando dos símbolos `+` en cada instrucción `System.out.println`. Verifica que Nuevo Foundation se imprima 3 veces. En otras palabras, tu consola debería verse así después de ejecutar el programa:

        Nuevo Foundation
        Nuevo Foundation
        Nuevo Foundation
{{% /notice %}}