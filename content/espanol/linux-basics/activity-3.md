---
title: "Activity 3 - Explore Current Directory"
description: "Use Linux commands to view the contents of the current directory"
date: 2022-09-23
difficulty: "Intermediate"
weight: 6
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/dSsed9cR9QI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## ¿Cómo exploras el directorio?

Para ver los archivos en el directorio actual, usamos el comando `ls`. Significa "List" (listar).

Pruébalo:

```
ls
```

![ls command](../images/03_ls-command.png?classes=border,shadow)

### ¿Cómo obtengo más información sobre los archivos en este directorio?

Pruébalo:

```
ls -l
```
<img src="../images/../images/03_ls-l.png" height="500" alt="ls -l command"/>

La opción `-l` en el comando anterior indica a `ls` que muestre la información en formato largo.

## ¿Qué información se muestra?

Examinemos la línea superior del ejemplo anterior de izquierda a derecha, para el directorio `Videos`:

![ls -l command explained](../images/03_ls-l-numbers.png?classes=border,shadow)

1. <span style="color:green">verde</span>: los permisos del archivo. El primer carácter `d` indica que **Videos** es un directorio. Si fuera un `-`, significaría que **Videos** es un archivo.
2. <span style="color:red">rojo</span>: el número de **enlaces (links)** para este archivo. El directorio **Videos** tiene 2 _enlaces_.
3. <span style="color:purple">púrpura</span>: el usuario que posee este archivo. El usuario `nuvi` es el propietario del directorio **Videos**.
4. <span style="color:white;background-color:#232b36">blanco</span>: el grupo al que pertenece este archivo. Aquí, el directorio **Videos** pertenece al grupo `nuvi`.
5. <span style="color:#ffc000">amarillo</span>: el tamaño del archivo en **bytes**. El tamaño del directorio **Videos** es 4096 bytes.
6. <span style="color:#ed7d31">naranja</span>: fecha y hora en que se creó el archivo.
7. <span style="color:#2e75b6">azul</span>: nombre del directorio.