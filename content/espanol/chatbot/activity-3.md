---
title: "Activity 3: Add your own categories"
draft: false
weight: 7
---

## Añade más categorías

En este momento, nuestro bot solo puede responder a "Hello". Añadamos algunas categorías más para que el bot pueda responder a más cosas.

1. Si el usuario dice "¿Cómo te llamas?" el bot debería responder "Me llamo Chatbot".
2. Si el usuario dice "¿Cuál es tu color favorito?" el bot debería responder "Mi color favorito es el azul".
3. Si el usuario dice "¿Cuál es tu comida favorita?" el bot debería responder "Mi comida favorita es la pizza".

Como recordatorio, aquí está la estructura básica de una categoría:

```
<category>
    <pattern>HELLO</pattern>
    <template>
        Hello, World!
    </template>
</category>
```

{{% notice tip %}}

Recuerda: al escribir el pattern, usa MAYÚSCULAS y evita la puntuación. Por ejemplo, si quieres hacer coincidir "¿Cómo te llamas?", deberías escribir el pattern como "COMO TE LLAMAS".

{{% /notice %}}

{{% notice tip %}}

Recuerda guardar el archivo cada vez que modifiques las categorías y quieras interactuar con el chatbot.

{{% /notice %}}

Prueba a añadir estas categorías a tu bot y pruébalas usando el widget de chat. En este punto, el bot debería responder a "Hello", "¿Cómo te llamas?", "¿Cuál es tu color favorito?" y "¿Cuál es tu comida favorita?".