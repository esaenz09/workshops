---
title: "Activity 2: Setup PandoraBots"
draft: false
weight: 5
---

## AIML
Usaremos AIML para crear nuestro chatbot. AIML significa **Artificial Intelligence Markup Language**. Si alguna vez has usado HTML para crear un sitio web, verás que AIML es muy similar. Antes de que podamos empezar a escribir AIML, necesitamos registrarnos para obtener una cuenta en PandoraBots.

## Pandorabots
Ve a [https://www.pandorabots.com/] y haz clic en **Sign Up**. Introduce un correo electrónico y una contraseña para crear una cuenta. Alternativamente, puedes registrarte usando una cuenta de Google, Facebook, Twitter o Github. Si te lo piden, elige la opción de prueba gratuita.

## Create a new bot
Una vez que te hayas registrado, deberías ver una página como esta:

<p style="text-align: center;"><img src="../img/pandorabots_1.png" alt="new account landing page on pandorabots" width="40%"/></p>

Para crear un nuevo bot, usa el botón “+” junto a My Bots en el panel de navegación. Dale un nombre y haz clic en “Create Bot”.

<p style="text-align: center;"><img src="../img/pandorabots_2.png" alt="creating a new bot on pandorabots" width="40%"/></p>

## Bot Editing
Una vez que hayas creado un bot, el nombre del bot aparecerá en el panel de navegación. Haz clic en **Edit** debajo del nombre de tu bot y luego elige **Code Editor** para ir al Editor.

<p style="text-align: center;"><img src="../img/pandorabots_3.png" alt="editing a bot on pandorabots" width="40%"/></p>

El Editor es donde escribirás archivos AIML y categorías que permitirán que tú y otros conversen con tu bot.

Usa el menú File para crear un nuevo archivo AIML llamado greetings.

<p style="text-align: center;"><img src="../img/pandorabots_4.png" alt="adding a new file on pandorabots" width="40%"/></p>

<p style="text-align: center;"><img src="../img/pandorabots_5.png" alt="adding a new file on pandorabots" width="40%"/></p>

## Hola Mundo

Copia el código de la siguiente categoría en el editor de texto entre las etiquetas de inicio ```<aiml>``` y fin ```</aiml>```:

```
<category>
    <pattern>HELLO</pattern>
    <template>
        Hello, World!
    </template>
</category>
```

Una vez completado, guarda tu archivo desde el menú desplegable “File”.

<p style="text-align: center;"><img src="../img/pandorabots_6.png" alt="adding a new file on pandorabots" width="40%"/></p>

## Probar tu bot
El Chat Widget te permite hablar con tu bot. Haz clic en el icono de "chat bubbles" en la esquina inferior derecha para empezar a hablar con tu bot. Escribe `Hello` y deberías recibir la respuesta que acabas de programar: `“Hello, world!”`

<p style="text-align: center;"><img src="../img/pandorabots_7.png" alt="adding a new file on pandorabots" width="40%"/></p>