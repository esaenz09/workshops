---
title: "Categories"
draft: false
weight: 6
---

## Fundamentos de AIML
La unidad básica de AIML es la **category**. Una **category** consiste en un **pattern** y un **template**. El **pattern** es lo que el usuario le dice al bot. El **template** es la respuesta que el bot le da al usuario. 

Al observar el siguiente ejemplo, podemos ver que el pattern es "HELLO" y el template es "Hello, World!". Cuando el usuario dice "HELLO", el bot responderá con "Hello, World!". Ten en cuenta que la coincidencia de patrones no distingue entre mayúsculas y minúsculas, por lo que el bot responderá a "hello", "HELLO", "Hello" y "HeLlo" de la misma manera.

```
<category>
    <pattern>HELLO</pattern>
    <template>
        Hello, World!
    </template>
</category>
```

{{% notice info %}}

Al escribir el pattern, recomendamos escribirlo todo en MAYÚSCULAS y evitar el uso de puntuación. Así que si quieres coincidir con "What is your name?", deberías escribir el pattern como "WHAT IS YOUR NAME". Pandora eliminará cualquier puntuación en la entrada del usuario antes de comparar con el pattern.

{{% /notice %}}