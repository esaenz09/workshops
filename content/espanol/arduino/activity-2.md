---
title: "Activity 2 -  Joystick with Serial Output"
draft: false
weight: 5
---

## Cableado del joystick

Ahora que entiendes cómo podemos hacer que el sistema suministre señales desde el programa (salidas) y usarlas para controlar LEDs, veamos cómo podemos implementar entradas dinámicas en el sistema. Para esta actividad usaremos una entrada de joystick, similar a las empleadas en consolas de videojuegos.

![Alt Text: Wiring Diagram for Joystick module](../img/act2_Joystick.png)

1.	Conecta un extremo de un cable puente a GND del joystick y el otro extremo a GND del Elegoo.  
2.	Conecta un extremo de un cable puente a +5V del joystick y el otro extremo a 5V del Elegoo.  
3.	Conecta un extremo de un cable puente a VRx del joystick y el otro a A0 (pin analógico 0) del Elegoo.  
4.	Conecta un extremo de un cable puente a VRy del joystick y el otro a A1 (pin analógico 1) del Elegoo.  
5.	Conecta un extremo de un cable puente a SW del joystick y el otro a 2 (pin digital 2) del Elegoo.  
6.	Conecta la placa Arduino por USB a tu PC y abre la aplicación Arduino IDE.

## Reconocer e imprimir entradas analógicas
Usaremos nuevamente un código de ejemplo para nuestros programas. Esta vez lo obtendremos del sitio web de Elegoo. Copia lo siguiente en tu Arduino IDE.
``` c++
//www.elegoo.com
//2016.12.09

// Números de pines de Arduino
const int SW_pin = 2; // pin digital conectado a la salida del interruptor
const int X_pin = A0; // pin analógico conectado a la salida X
const int Y_pin = A1; // pin analógico conectado a la salida Y

void setup() {
  pinMode(SW_pin, INPUT);
  digitalWrite(SW_pin, HIGH);
  Serial.begin(9600);
}

void loop() {
  Serial.print("Switch:  ");
  Serial.print(digitalRead(SW_pin));
  Serial.print("\n");
  Serial.print("X-axis: ");
  Serial.print(analogRead(X_pin));
  Serial.print("\n");
  Serial.print("Y-axis: ");
  Serial.println(analogRead(Y_pin));
  Serial.print("\n\n");
  delay(500); 
}
```
7.	Ahora haz clic en el botón de subir (Upload) para desplegar el programa en el Arduino.  
8.	Haz clic en el botón “Serial Monitor” en la esquina superior derecha de la pantalla para mostrar la consola.  
![Atl Text: Screen Shot of Arduino IDE showing the location of the serial monitor button](../img/SerialMonitor-button.png)  
9.	Fíjate cómo los valores X e Y cambian cuando mueves el joystick.