---
title: "Activity 1: Blinking LED"
draft: false
weight: 4
---

## Wiring Our Blinking LED

Para introducirte en este sistema, vamos a encender y APAGAR un LED. Con esto podemos aprender lo básico de los circuitos y cómo nuestro programa puede ejecutar y manipular componentes.

![Alt Text: Wiring Diagram for the LED](../img/act1_LED1.png)

1. Conecta la patilla larga (ánodo) de tu LED al pin 25J y la patilla corta (cátodo) en cualquier punto de la línea azul [-].
2. Coloca una resistencia de 220 Ω con una pata en 25H y la otra en cualquier punto de la línea roja [+].
3. Conecta un extremo de un cable dupont en la misma línea roja [+] del Breadboard que en el paso 2 y el otro extremo al 5V del Elegoo.
4. Conecta un extremo de un cable dupont en 31Z del Breadboard y el otro al GND (masa) del Elegoo.
5. Conecta la placa Arduino por USB a tu PC y abre la aplicación Arduino IDE.

{{% notice info %}}
¡Usar colores para los cables es habitual y realmente útil! Aquí usamos rojo para el polo positivo y negro para el negativo, pero el color no importa siempre que recuerdes qué representa cada uno.
{{% /notice %}}

## Opening LED Sample Code

6. Haz clic en File -> Examples -> 01.Basics -> Blink

![Alt Text: Picture showing how to find Blink sample code](../img/Blink-sample-code.png)

7. Ahora haz clic en el botón upload para desplegar el programa en el Arduino.

{{% notice info %}}
EXTRA: Fíjate en la duración del encendido y apagado del LED. ¿Qué crees que podrías cambiar en el programa para modificar ese tiempo?
Si respondiste el número 1000 en delay(1000); ¡estÁS CORRECTO!
Cambia ese número (no olvides presionar el botón upload de nuevo).
¿Notas la diferencia? ¿Por qué crees que 1000 equivale a 1 segundo? ¿Cuánto sería 10 minutos? ¿Por qué?
{{% /notice %}}