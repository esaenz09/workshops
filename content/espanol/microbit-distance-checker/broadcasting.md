---
title: "Broadcasting a Signal"
date: 2019-07-25T13:24:17-07:00
weight: 2
draft: false
---

## Encender la radio

Usaremos la radio Bluetooth de tu micro:bit para averiguar qué tan lejos estás de otros micro:bits. Lo primero que debemos hacer es encender la radio y sintonizarla en un canal. Haz clic en la sección que dice Radio. Es la sección de color rosa, la quinta desde arriba. Elige "radio set group 1" y arrástralo dentro del bloque azul "on start" en el área de trabajo. Asegúrate de usar el mismo número de grupo que los demás. Si usan números de grupo distintos, sus micro:bits no podrán comunicarse entre sí. Tu área de trabajo debería verse como la siguiente cuando termines:

![MakeCode menu showing the Radio section selected](../img/radioMenu.png)
![MakeCode workspace showing the "radio set group" block in the "on start" block](../img/setRadioGroup.png)

## Transmitir una señal

Ahora que nuestros micro:bits están configurados para escuchar, necesitamos enviar una señal para que la detecten. Haz clic de nuevo en la sección Radio. Esta vez arrastra el bloque "radio send number 0" dentro del bloque azul "forever" en tu área de trabajo. Esto hará que tu micro:bit envíe continuamente ese número a cualquier dispositivo que esté escuchando en el mismo grupo.

![MakeCode workspace showing the "radio send number" block in the "forever" block](../img/radioSendNumber.png)

Manténlo claro para principiantes. Preserva los términos técnicos, la sintaxis del código y el formato. Solo traduce los comentarios que expliquen conceptos. Adapta las referencias culturales de forma apropiada. Don't translate the header key title; don't translate the image html