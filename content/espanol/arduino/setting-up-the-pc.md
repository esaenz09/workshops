---
title: "Setting up the PC"
draft: false
weight: 2
---

## Conociendo el Arduino IDE

Descarga e instala el Arduino IDE desde:

* the Microsoft Store (quicker install) - <https://www.microsoft.com/store/productId/9NBLGGH4RSD8>
* or from the Arduino website <https://www.arduino.cc/en/Main/Software> (pick the latest version)

Una vez que el software esté instalado en tu ordenador, ábrelo. Este es el Arduino IDE y es el lugar donde ocurrirá toda la programación. Tómate un momento para explorar y familiarizarte con él.

![Alt Text: Labeled picture of the Arduino IDE](../img/ArduinoIDE-labeled.png)
*<https://www.makerspaces.com/simple-arduino-projects-beginners/>*

1. Menu Bar: Te da acceso a las herramientas necesarias para crear y guardar sketches de Arduino.
2. Verify Button: Compila tu código y comprueba si hay errores de ortografía o de sintaxis.
3. Upload Button: Envía el código a la placa que esté conectada, por ejemplo Arduino Uno. Las luces de la placa parpadearán rápidamente durante la carga.
4. New Sketch: Abre una ventana nueva con un sketch en blanco.
5. Sketch Name: Cuando el sketch esté guardado, aquí se muestra el nombre del mismo.
6. Open Existing Sketch: Permite abrir un sketch guardado o uno de los ejemplos almacenados.
7. Save Sketch: Guarda el sketch que tienes abierto actualmente.
8. Serial Monitor: Cuando la placa esté conectada, mostrará la información serial de tu Arduino.
9. Code Area: Esta área es donde compones el código del sketch que indica a la placa qué hacer.
10. Message Area: Esta área te informa sobre el estado de guardado, compilación del código, errores y más.
11. Text Console: Muestra los detalles de los mensajes de error, el tamaño del programa compilado e información adicional.
12. Board and Serial Port: Indica qué placa se está usando y a qué puerto serial está conectada.

## Conecta tu Arduino

En este punto estás listo para conectar tu Arduino a tu ordenador. Conecta un extremo del cable USB al Arduino Uno y el otro extremo al puerto USB de tu ordenador.

Una vez que la placa esté conectada, necesitarás ir a Tools luego a Board y finalmente seleccionar Arduino Uno.

![Alt Text: Screenshot of Arduino IDE showing how to select our board type](../img/board-select.png)

A continuación, debes indicar al Arduino qué puerto estás usando en tu ordenador.

Para seleccionar el puerto, ve a Tools luego a Port y selecciona el puerto que diga Arduino.

![Alt Text: Screenshot of Arduino IDE showing how to select the COMM port](../img/COMM-port.png)