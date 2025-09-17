---
title: "C: El Proceso de Depuración"
description: "Una Introducción a la Depuración de Programas"
date: 2021-10-13T00:00:00Z
difficulty: "Intermediate"
prereq: "C"
icon: ""
draft: false
---

## Introducción

Entonces, has aprendido los conceptos básicos de un lenguaje de programación. Probablemente hayas dominado el arte de `“Hello World”` y hayas empezado un proyecto personal o seguido suficientes tutoriales como para poder convertir una idea en código.

Sin embargo, ¿qué ocurre cuando tu código no compila? Los principiantes en programación suelen buscar en internet para ver si otros han encontrado problemas similares. Esto puede resultar tedioso, ya que tendrías que recurrir a la red cada vez que encuentres un error.

¿Y qué pasa cuando tu programa compila, pero no funciona como esperabas? (es decir, ¿has encontrado **un bug? 🪲)

Volver atrás para arreglar tu código puede ser un desafío incluso más difícil que escribirlo. Aprender a manejar estos errores y fallos requiere habilidad, paciencia y experiencia. En este taller, desglosaremos el proceso básico para depurar tu código. Recuerda que la depuración forma parte de todos los lenguajes de programación.

{{% panel theme="info" header="Why call it a bug?"%}}
The first recorded programming bug was recorded all the way back in 1947 when a moth decided to be in the wrong place. Check out <a href="https://education.nationalgeographic.org/resource/worlds-first-computer-bug" target="_blank">The World’s First Computer Bug.</a>
{{% /panel %}}

## Sobre este taller

Este taller asume que entiendes y puedes escribir código en el lenguaje de programación **C**. Los ejemplos usados en este taller hacen uso de estructuras de datos y algoritmos, temas que normalmente se enseñan en un curso introductorio de informática. Tendremos una breve explicación de ellos, pero está pensada como un repaso para que tengas una idea de lo que hace el código de ejemplo. Este taller también asume que ya tienes una cuenta en [Replit](https://replit.com) y estás familiarizado con Replit.

## Replit y la línea de comandos

Vamos a intentar usar Replit para ejecutar algún código y familiarizarnos más con la línea de comandos. Haz clic en el botón "Launch Replit" más abajo y haz un fork del programa. Cuando se abra el programa en Replit, abre la pestaña **Shell**.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/Debugging-Samples-C" target="_blank">Launch Replit</a>

Primero compilemos nuestro código. Dentro de la pestaña shell, escribe lo siguiente y pulsa **ENTER**:

```bash
make HelloWorld
```

Después de compilar nuestro código, necesitamos usar un comando distinto para ejecutarlo. Escribe lo siguiente y pulsa **ENTER**:

```bash
./examples/HelloWorld
```

¡Deberías ver el texto `Hello, World!` impreso en la shell!

{{% panel theme="info" header="Why use the command line?"%}}
The command line may seem unintuitive and not user-friendly to beginners. However, knowing how to use it is extremely important for your programming career. We'll be using it to run `gdb` and `valgrind` later in the workshop, so the more experience you have with it, the better!

The examples were written on a single Replit. We'll be providing all the commands you need to know to compile and run them, so don't worry if you haven't used the command line so far. 
{{% /panel %}}

## Contenido del taller

{{% children /%}}; mantenerlo claro para principiantes. 
        Preservar términos técnicos, la sintaxis del código y el formato. Sólo traducir los comentarios que expliquen conceptos.
        Adaptar las referencias culturales de forma apropiada. No traducir el valor de la clave del encabezado; no traducir el HTML de imágenes.