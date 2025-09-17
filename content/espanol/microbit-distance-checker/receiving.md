---
title: "Receiving a Message"
date: 2019-07-25T13:24:17-07:00
weight: 3
draft: false
---

Ahora que estamos enviando mensajes y escuchando por ellos, necesitamos usar esa información para averiguar la distancia entre los micro:bits. Para ello, necesitamos saber qué tan fuerte es la señal que estamos recibiendo. Vuelve a la sección Radio y, esta vez, arrastra el bloque "on radio received (receivedNumber)" a un lugar vacío de tu espacio de trabajo. No debe estar dentro de ningún otro bloque.

This block tells our micro:bit to do something whenever it gets a number sent to it from another micro:bit.

!["On radio received" block added to the workspace](../img/onRadioReceived.png)

A continuación, haz clic en la sección roja Variables y luego haz clic en "Make a Variable...". En el cuadro de texto, escribe "strength" como nombre de tu nueva variable, y luego haz clic en "Ok ✔".

![MakeCode menu showing the Variables section selected](../img/makeVariable.png)
![The variable name pop-up window](../img/variableModal.png)

Ahora, vuelve al menú Variables y arrastra "set strength to 0" dentro del bloque rosado "on radio received (receivedNumber)". Luego regresa al menú Radio y arrastra "received packet (signal strength)" encima del `0️` en "set strength to 0️". Cuando termines, tu espacio de trabajo debería verse algo así:

![Workspace with on start, forever, and received packet blocks filled in](../img/savedRSSI.png)

Las variables son simplemente lugares donde podemos almacenar información con un nombre amigable para dejar claro qué se guarda dentro. Así que, al crear una variable llamada `strength`, lo que hacemos es reservar un espacio para guardar un valor; en este caso, la intensidad de señal medida del mensaje que recibimos. Luego podemos usar simplemente el nombre `strength` en cualquier lugar donde queramos comprobar el valor actual o compararlo con otra cosa. Si más tarde recibimos un nuevo mensaje con una señal más fuerte o más débil, el valor de `strength` se actualiza automáticamente a ese nuevo valor. De ahí el bloque "on radio received": cada vez que recibimos un nuevo mensaje, el valor de `strength` se actualiza a la intensidad de señal más reciente sin que tengas que hacer nada manualmente.