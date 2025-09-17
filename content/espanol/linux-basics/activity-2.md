---
title: "Activity 2 - Determine User Location"
description: "Usa un comando de Linux para determinar en qué directorio te encuentras actualmente"
date: 2022-09-23
difficulty: "Intermedio"
weight: 5
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/v1XLyLuQQyA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Antes de que podamos detener a los hackers, necesitamos aprender a navegar por el sistema de archivos de Linux.
    </div>
</div>

## ¿Qué es un sistema de archivos?

Un sistema de archivos es una colección estructurada de archivos y datos en un disco o unidad de un ordenador. El nivel más alto de un sistema de archivos se conoce como la "raíz". Puedes pensar en ella como el comienzo del sistema de archivos.

{{% notice tip %}}
Dato curioso: a menudo se describe a los sistemas de archivos como un "árbol". Esto es porque el sistema de archivos se parece a un árbol invertido, con cada carpeta como una rama o una hoja. Por ejemplo, tu sistema de archivos podría verse como en la imagen a continuación.

<img src="../images/filesystem-tree.png" height="500" alt="Picture of a filesystem tree"/>

{{% /notice %}}

En un equipo con Windows, puedes explorar el sistema de archivos de la unidad "C:\" usando el "Explorador de archivos" como se muestra abajo:

![Picture of a Windows file explorer](../images/filesystem-windows.png?classes=border,shadow)

En un Mac, puedes explorar el sistema de archivos de tu usuario en el "Finder" como se muestra abajo:

![Picture of the Mac file finder](../images/home-folder-mac.jpg?classes=border,shadow)

## ¿Dónde estás en el sistema de archivos?

Queremos averiguar cuál es nuestro "directorio de trabajo actual". Esta es la ubicación en el sistema de archivos en la que te encuentras actualmente.

El comando de Linux `pwd` mostrará tu ubicación actual. Esto significa "Print Working Directory" (imprimir el directorio de trabajo). ¡Pruébalo!

```
pwd
```

<!---!![pwd command](../images/02_pwd.png?classes=border,shadow) --->
<img src="../images/02_pwd.png" alt="pwd command" style="width:700px;"/>

La salida anterior es `/home/nuvi` y su significado se explica a continuación:

- `/`: Este es el símbolo para el directorio raíz de este sistema de archivos.
- `/home`: Esta es la ruta del directorio home, que está ubicado dentro del directorio raíz.
- `/home/nuvi`: Esta es la ruta del directorio nuvi, que está ubicado dentro del directorio home. La salida se detiene aquí, lo que significa que `/home/nuvi` es el directorio de trabajo actual en el que nos encontramos.
- Este proceso de ir entrando en el sistema de archivos a través de cada carpeta puede continuar durante muchos más pasos en algunos casos.
- La ruta mostrada y descrita arriba se llama la <b>ruta absoluta</b>, porque es la ruta desde el directorio actual hasta el directorio raíz.

## ¿Cómo me muevo por el sistema de archivos?

Para moverte a un directorio diferente, usa el comando `cd`. Esto significa "Change Directory" (cambiar directorio). El formato de este comando es `cd [nombre_del_directorio]`.

<!---![cd command](../images/02_cd.PNG?classes=border,shadow) --->
<img src="../images/02_cd.PNG" alt="cd command" style="width:700px;"/>

En la salida anterior, puedes ver que cuando escribimos `pwd` de nuevo, el directorio de trabajo en el que estamos ahora es Desktop. Prueba `cd ..`.

Intenta un ejemplo más de `cd` a continuación:

```
cd ..
```

<!-- ![cd command](../images/02_cdDotDot.PNG?classes=border,shadow) -->
<img src="../images/02_cdDotDot.PNG" alt="cd command" style="width:700px;"/>

Los `..` después del comando cd te llevan un nivel hacia arriba en el árbol del sistema de archivos. La salida de `pwd` ahora muestra que hemos vuelto al punto de partida. Comenzamos en el directorio nuvi, bajamos al árbol a `Desktop` con `cd Desktop`, y luego subimos con `cd ..`.

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Buen trabajo! A continuación veremos cómo explorar los propios directorios.
    </div>
</div>