---
title: "What is a micro:bit?"
date: 2019-07-25T13:24:17-07:00
weight: 1
draft: false
---

## ¿Qué es un micro:bit?

¡Un micro:bit es un microcontrolador programable! Se puede programar desde cualquier navegador web en varios lenguajes como JavaScript, Python, Scratch y Blocks. Para nuestra sesión de hoy usaremos MakeCode Blocks.

Tu micro:bit tiene muchas funcionalidades accionables y sensores, entre ellos:

- 25 LEDs direccionables individualmente
- 2 botones físicos
- 2 pines de Entrada/Salida (IO)
- Sensor de brújula
- Acelerómetro (sensor de movimiento)
- Bluetooth

<img src="../img/microbit-hardware-access.jpg" alt="microbit components" style="width:800px;"/>

Si quieres saber más sobre cada componente individual y todas las características que trae tu micro:bit, puedes hacer clic [aquí](https://micro:bit.org/guide/features/).

Saca el micro:bit y el resto de los componentes de la bolsa. Debes tener un micro:bit, 2 baterías, un cable micro USB y el portapilas (la caja negra con los cables rojo y negro saliendo de ella). Si te falta algo o necesitas ayuda, pregunta a uno de los instructores.

## Uso del simulador

Aunque no es tan divertido como tener el hardware físico, también puedes usar el simulador para ver tu código en funcionamiento. Busca las imágenes de micro:bits en el lado izquierdo de la pantalla. Si no las ves, busca el símbolo ">" a la izquierda y haz clic para mostrar el simulador. En los micro:bits simulados, encuentra la antena de radio Bluetooth. Se parece a una onda cuadrada amarilla:

<img src="../img/simulatorStart.png" alt="Image of simulated micro:bits with the radio highlighted" style="width:500px;"/>

Si colocas el cursor del ratón sobre esta antena con forma de onda, la intensidad real de la señal aparecerá junto a ella. Entonces puedes hacer clic en la antena y arrastrar el cursor hacia la izquierda para disminuir la intensidad de la señal o hacia la derecha para aumentarla. Si consigues que la señal sea lo bastante fuerte (`strength > -67`), el otro micro:bit se actualizará para mostrar una cara fruncida. Debilita la señal de nuevo para que el micro:bit vuelva a sonreír.

<img src="../img/showingRSSI.png" alt="Sowing RSSI" style="width:300px;"/> 
<img src="../img/sadSimulator.png" alt="Image of sad simulator" style="width:300px;"/>

¡Ahora, vamos a programar!