---
title: "Echoing Wildcards"
draft: false
weight: 9
---

## Introducción a la etiqueta ```<star />```
Aprendamos una herramienta más para permitir que nuestro chatbot tenga respuestas más interesantes. En la lección anterior aprendimos cómo podemos usar el comodín ```*``` para coincidir con cualquier palabra o frase. Pero, ¿qué pasa si queremos usar la palabra o frase que el usuario escribió dentro de nuestra respuesta? Por ejemplo, si el usuario nos dice cuál es su color favorito, queremos que la respuesta del bot incluya ese color favorito. Podemos hacer esto usando la etiqueta ```<star />```.

La etiqueta ```<star />``` es una etiqueta especial que nos permite usar la palabra o frase que el usuario escribió en nuestra respuesta. Veamos cómo funciona.

```
<category>
    <pattern>MY FAVORITE COLOR IS *</pattern>
    <template>
        Your favorite color is <star />.
    </template>
</category>
```

Veamos paso a paso cómo funciona esta categoría. El patrón "MY FAVORITE COLOR IS *" coincidirá con cualquier entrada que empiece con "MY FAVORITE COLOR IS" seguida de cualquier palabra o frase. Así que el patrón coincidirá con "MY FAVORITE COLOR IS BLUE", "MY FAVORITE COLOR IS RED", "MY FAVORITE COLOR IS GREEN", y así sucesivamente. La etiqueta ```<star />``` capturará la palabra o frase que el usuario escribió y la usará en la respuesta. Entonces, si el usuario ingresa "MY FAVORITE COLOR IS BLUE", "blue" es la palabra representada por el comodín, por lo que cuando el chatbot responda, ```<star />``` será reemplazado por "blue". El bot responderá "Your favorite color is blue".

Aquí hay algunos ejemplos más de entradas y salidas de esta categoría:

Entrada | Salida 
---|--------------
MY FAVORITE COLOR IS BLUE | Your favorite color is blue.
MY FAVORITE COLOR IS RED | Your favorite color is red.
MY FAVORITE COLOR IS GREEN | Your favorite color is green.

Mantenerlo claro para principiantes. Preserva los términos técnicos, la sintaxis del código y el formato. Solo traduce los comentarios que expliquen conceptos. Adapta las referencias culturales según corresponda. No traduzcas la clave del encabezado title; no traduzcas el HTML de imágenes.