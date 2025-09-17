---
title: "Wildcards"
draft: false
weight: 8
---

## Wildcards
Es posible que te estés dando cuenta de que lleva mucho trabajo escribir una categoría para cada posible forma en que un usuario podría hacer una pregunta. Por ejemplo, actualmente el bot responderá a "Hello" con "Hello, world". Pero ¿qué pasa si el usuario dice "Hello there" o "Hello chatbot"? Tendríamos que escribir una nueva categoría para cada uno de esos casos. Afortunadamente, hay herramientas adicionales que podemos usar para que nuestro bot sea más flexible.

Una de estas herramientas es el **wildcard**. Un **wildcard** es un carácter especial que coincide con cualquier palabra o frase. Veamos cómo funciona.

```
<category>
    <pattern>HELLO *</pattern>
    <template>
        Hi!
    </template>
</category>
```

El símbolo `*` puede capturar una o más palabras en la entrada del usuario. Con esta nueva categoría, el chatbot ahora responderá con "Hi!" a cualquier entrada que comience con "Hello" seguida de cualquier palabra. Así que el patrón "HELLO *" coincidirá con "HELLO THERE" y "HELLO CHATBOT" y "HELLO WORLD" y "HELLO EVERYONE" y así sucesivamente, manteniendo la explicación clara para principiantes.