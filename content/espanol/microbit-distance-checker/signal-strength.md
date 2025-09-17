---
title: "Interpreting Signal Strength"
date: 2019-07-25T13:24:17-07:00
weight: 4
draft: false
---

Ahora que nuestro micro:bit sabe qué tan fuerte es la señal que está recibiendo, necesitamos usar eso para averiguar qué tan cerca estamos. Haz clic en la sección Logic y toma el bloque "if true then / else". Arrástralo dentro del radio received block, justo debajo de donde establecemos la variable strength. Vuelve a la sección Logic y arrastra la comparación 0 = 0 sobre el true en la línea "if true then". Tu código ahora debería verse así:

![Workspace with if/then/else statement added to event block](../img/addedLogic.png)

A continuación, le diremos a nuestro microcontrolador micro:bit cómo determinar si estamos a 6 feet (2 meters) de distancia. Abre el menú Variables y selecciona la burbuja que solo dice "strength" y arrástrala sobre el primer cero en nuestro bloque if para que diga `if strength = 0 then`. Ahora, haz clic en el signo igual (=) para que aparezca una lista de símbolos diferentes. Elige el símbolo mayor que (>). Por último, haz clic en el último cero en nuestra sentencia if y reemplázalo con `-67`. Tu bloque rosa "on radio received" debería verse ahora así:

![Workspace with if/then/else statement added to event block](../img/completedCondition.png)

Quizás te estés preguntando: "¿Por qué -67? Parece un número aleatorio." -67 dBm (decibel-milliwatts) simplemente es el nivel de potencia que ya medimos con anterioridad cuando dos micro:bits están a 6 feet de distancia. Diferentes radios Bluetooth, como el de tu teléfono, podrían tener una intensidad distinta a la misma distancia. Cuanto más cerca esté tu señal de 0, más fuerte es y más cerca estás del otro radio. Una intensidad de señal más alejada de 0 es más débil, lo que significa que probablemente también estés más lejos del radio.

Eso significa que si la señal que recibimos es más fuerte que -67 dBm (`strength > -67`), nuestros radios micro:bit están a menos de 6 feet entre sí. Pero si la señal es más débil que eso, nuestros radios deben estar a más de 6 feet de distancia.