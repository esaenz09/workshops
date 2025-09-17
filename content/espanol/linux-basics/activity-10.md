---
title: "Activity 10 - Let's move and replace"
description: "Use Linux commands to move and copy files"
date: 2022-09-23
difficulty: "Intermediate"
weight: 13
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/LPcQW4oGK6g" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Genial, ahora que el archivo malicioso de los hackers ya no nos causará más problemas, restauremos el archivo antiguo para que todo vuelva a funcionar correctamente.
    </div>
</div>

### Cómo arreglar el secret-message

El comando `mv` también puede usarse para reemplazar el archivo de destino con el archivo de origen.  
El formato es: `mv [nombre de archivo origen] [nombre de destino]`.

Reemplaza el secret-message alterado con la copia de seguridad que encontramos anteriormente.  
Movamos el archivo al nuevo directorio que creamos.

![mv command](../images/Act10.1.png?classes=border,shadow)

---

### Haz una copia de seguridad de tus archivos

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Esa copia de seguridad anterior nos sirvió para arreglar el archivo manipulado. Hagamos una copia de seguridad de los archivos en nuestro directorio.
    </div>
</div>

`cp` es un comando que copia un archivo de una ubicación a otra.  
El formato es: `cp [nombre de archivo origen] [nombre de archivo destino]`.

Haz una copia del archivo que creaste y de `secret-message.txt`.

![cp command](../images/Act10.2.png?classes=border,shadow)