---
title: "Activity 3 - Joystick & LEDs"
draft: false
weight: 6
---

## Actividad 3 - Joystick + LEDs

![Alt Text: Wiring Diagram For Connecting Joystick and 5 LEDs](../img/act3_joy+led.png)

Vamos a combinar la actividad 1 y la actividad 2. Vamos a controlar los LEDs en función de la entrada del joystick.
1.	Conecta un extremo de un cable jumper a GND en el joystick y el otro a 7X en la protoboard.
2.	Conecta un extremo de un cable jumper a +5V en el joystick y el otro a 5W en la protoboard.
3.	Conecta un extremo de un cable jumper a VRx en el joystick y el otro a A0 en la Elegoo.
4.	Conecta un extremo de un cable jumper a VRy en el joystick y el otro a GND en la Elegoo.
5.	Conecta un extremo de un cable jumper a SW en el joystick y el otro al pin 2 en la Elegoo.
6.	Inserta la pata larga (ánodo) de tu LED azul en el pin 8F y la pata corta (cátodo) en el pin 9F.
7.	Coloca una resistencia de 220 Ω con una pata en 8G y la otra en 4G.
8.	Conecta un extremo de un cable jumper a 4H en la protoboard y el otro al pin 11 en la Elegoo.
9.	Conecta un extremo de un cable jumper a 9G y el otro a 12Z (en cualquier lugar de la línea azul [-] de la protoboard).
10.	Inserta la pata larga (ánodo) de tu LED amarillo en el pin 14J y la pata corta (cátodo) en el pin 15J.
11.	Coloca una resistencia de 220 Ω con una pata en 14I y la otra en 10I.
12.	Conecta un extremo de un cable jumper a 10J en la protoboard y el otro al pin 10 en la Elegoo.
13.	Conecta un extremo de un cable jumper a 15I y el otro a 18Z (en cualquier lugar de la línea azul [-] de la protoboard).
14.	Inserta la pata larga (ánodo) de tu LED rojo en el pin 21F y la pata corta (cátodo) en el pin 22F.
15.	Coloca una resistencia de 220 Ω con una pata en 17G y la otra en 21G.
16.	Conecta un extremo de un cable jumper a 17H en la protoboard y el otro al pin 9 en la Elegoo.
17.	Conecta un extremo de un cable jumper a 22G y el otro a 25Z (en cualquier lugar de la línea azul [-] de la protoboard).
18.	Inserta la pata larga (ánodo) de tu LED verde en el pin 14A y la pata corta (cátodo) en el pin 15A.
19.	Coloca una resistencia de 220 Ω con una pata en 10B y la otra en 14B.
20.	Conecta un extremo de un cable jumper a 10C en la protoboard y el otro al pin 8 en la Elegoo.
21.	Conecta un extremo de un cable jumper a 15B y el otro a 17X (en cualquier lugar de la línea azul [-] de la protoboard).
22.	Conecta los raíles azules [-] entre sí con un cable jumper.
23.	Conecta los raíles rojos [+] entre sí con un cable jumper.
24.	Conecta un extremo de un cable jumper a +5V en la Elegoo y el otro en cualquier punto de una de las líneas rojas [+].
25.	Conecta un extremo de un cable jumper a GND en la Elegoo y el otro en cualquier punto de una de las líneas azules [-].

## El Código

``` c++
int button=2;
int buttonState=0;
int buttonState1=0;

void setup() {
  pinMode(7,OUTPUT);
  pinMode(button,INPUT);
  digitalWrite(button,HIGH);
  Serial.begin(9600);

  pinMode(8,OUTPUT);
  pinMode(9,OUTPUT);
  pinMode(10,OUTPUT);
  pinMode(11,OUTPUT);
}
 
void loop() {

 int xValue = analogRead(joyX);
 int yValue = analogRead(joyY);

  Serial.print(xValue);
  Serial.print("\t");
  Serial.println(yValue);
  buttonState = digitalRead(button);
  Serial.println(buttonState);

  if (xValue>=0 && yValue<=20)
  {
    digitalWrite(10,HIGH);
  }
  else{digitalWrite(10,LOW);}

  if (xValue<=20 && yValue>=490)
  {
    digitalWrite(11,HIGH);
  }
  else{digitalWrite(11,LOW);}

  if (xValue>=1010 && yValue>=490)
  {
    digitalWrite(9,HIGH);
  }
  else{digitalWrite(9,LOW);}

  if (xValue>=490 && yValue>=1010)
  {
    digitalWrite(8,HIGH);
  }
  else{digitalWrite(8,LOW);}

  if (xValue>=1010 && yValue>=1010)
  {
    digitalWrite(9,LOW);
    digitalWrite(8,LOW);
  }

  if (buttonState==LOW)
  {
    Serial.println("Switch = High");
    digitalWrite(7,HIGH);
  }
  else{digitalWrite(7,LOW);}
  buttonState1=digitalRead(7);
  Serial.println(buttonState1);
  delay(100);
}

```