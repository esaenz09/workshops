---
title: "Setting Up Nuvi"
date: 2021-10-06T11:45:38-07:00
draft: true
weight: 3
---

Para comenzar a configurar a nuestro personaje principal, Nuvi, primero necesitamos importar los recursos del juego que queremos usar. Puedes importar tus propios recursos, o [descargar los recursos proporcionados](../files/Unity_game_images.zip). Para importarlos en Unity, debemos ir a la ventana Project y, dentro de la carpeta Assets, crear una nueva carpeta y nombrarla "Drawings".

![Creating a new folder](../img/2_1.png)

Arrastra todo lo que importaste a la carpeta Drawings.

A continuación, arrastra y suelta el dibujo de Nuvi en el Hierarchy. Nuvi debería aparecer ahora en la ventana Scene y en la Game. Como podemos ver en la ventana Game, Nuvi es demasiado grande. Para redimensionar a Nuvi, usaremos la herramienta Rect (Rect tool) en la esquina superior izquierda de Unity.

![Rect tool](../img/2_Unity_tools.png)

Luego haz clic y arrastra uno de los círculos azules que aparecen en las esquinas de Nuvi para redimensionarlo. Si ejecutamos el programa ahora mismo, Nuvi no hace nada: simplemente permanece quieto. Para que Nuvi pueda moverse, tenemos que añadir el componente "Rigidbody2D".

{{< notice info >}}
El componente Rigidbody2D permite que un GameObject sea manipulado por el motor de físicas de Unity.
{{< /notice >}}

Para añadir cualquier componente a un GameObject, haz clic en Nuvi como lo hiciste para redimensionarlo. Aparecerá la ventana Inspector a la derecha. Después haz clic en el botón "Add Component" y selecciona "Rigidbody2D" buscándolo y tecleando su nombre.

<img src="../img/2_AddComponent.png" alt="Before adding a component" width="400"/>
<img src="../img/2_Rigidbody2D.png" alt="After adding a component" width="400"/>

Ahora, si ejecutaras el programa, verías a Nuvi moviéndose lentamente hacia adelante. En realidad, ¡Nuvi está cayendo! Esto se debe a que en el componente Rigidbody2D, la "Gravity Scale" de Nuvi está establecida en 1, y la gravedad lo atrae hacia abajo. Como no queremos que Nuvi caiga en nuestro juego, tenemos que cambiar la gravedad a 0 en el Inspector.

Antes de continuar, debemos guardar con frecuencia para no perder el progreso. Para ello, puedes mantener pulsado Control + S (Command + S si usas Mac) o ir a la esquina superior izquierda de la pantalla y hacer clic en "Save" dentro del menú "File". Asegúrate de hacerlo con frecuencia mientras sigues este taller.