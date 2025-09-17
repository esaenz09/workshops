---
title: "Activity 4 - LCD Display"
draft: false
weight: 7
---

## Diagrama de conexión

Ahora que has dominado la salida de señales a LEDs, veamos cómo mostrar texto con una pantalla simple. Solo se usa 1 resistor (5K) para limitar el brillo de la pantalla. Intenta cablear esto según el diagrama sin instrucciones específicas.

![Alt Text: Wiring Diagram for Elegoo and LCD Display](../img/LCD-wiring.png)

## El código:
``` c++
//www.elegoo.com
//2016.12.9

/*
  Biblioteca LiquidCrystal - Hola Mundo

  Demuestra el uso de una pantalla LCD 16x2. La biblioteca LiquidCrystal
  funciona con todas las pantallas LCD compatibles con el
  controlador Hitachi HD44780. Hay muchas de ellas, y usualmente
  se pueden reconocer por la interfaz de 16 pines.

  Este sketch imprime "Hello World!" en la LCD
  y muestra el tiempo.

  El circuito:
 * Pin RS del LCD al pin digital 7
 * Pin Enable del LCD al pin digital 8
 * Pin D4 del LCD al pin digital 9
 * Pin D5 del LCD al pin digital 10
 * Pin D6 del LCD al pin digital 11
 * Pin D7 del LCD al pin digital 12
 * Pin R/W del LCD a tierra (GND)
 * Pin VSS del LCD a tierra (GND)
 * Pin VCC del LCD a 5V
 * Potenciómetro 10K:
 * extremos a +5V y tierra
 * cursor al pin VO del LCD (pin 3)

 Library originally added 18 Apr 2008
 by David A. Mellis
 library modified 5 Jul 2009
 by Limor Fried (http://www.ladyada.net)
 example added 9 Jul 2009
 by Tom Igoe
 modified 22 Nov 2010
 by Tom Igoe

 This example code is in the public domain.

 http://www.arduino.cc/en/Tutorial/LiquidCrystal
 */

// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);

void setup() {
  // configura el número de columnas y filas del LCD:
  lcd.begin(16, 2);
  // Imprime un mensaje en la LCD.
  lcd.print("Hello, World!");
}

void loop() {
  // coloca el cursor en la columna 0, línea 1
  // (nota: la línea 1 es la segunda fila, ya que la numeración empieza en 0):
  lcd.setCursor(0, 1);
  // imprime el número de segundos desde el reinicio:
  lcd.print(millis() / 1000);
}
```