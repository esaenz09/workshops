---
title: "Activity 11 - Store and protect files"
description: "Usa comandos de Linux para comprimir y archivar archivos."
date: 2022-09-23
prereq: "Ninguno."
difficulty: "Intermedio"
weight: 14
---

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Thanks so much for helping us fix my machine! Now let's get everything up into one nice package.
    </div>
</div>

### Asegura tus archivos para que no vuelvan a ser alterados

`tar` es un comando que crea y extrae archivos archivados.

{{% notice info %}}
Un archive es una colección de archivos de archivo. Un archivo de archive contiene los datos comprimidos de uno o más archivos.

`zip` es un comando que comprime un conjunto de archivos. El formato es: `zip [name of zip file] [filenames to be zipped]`
{{% /notice %}}

El formato es: `tar [filenames]`.

| flags | Usos                                |
| :---- | :---------------------------------- |
| -c    | crea un archivo                     |
| -x    | extrae un archivo                   |
| -f    | crea un archivo con el nombre dado  |

¡Usa `tar` para asegurar tu directorio `files`! Debes crear un archivo con el nombre `files.tar.gz`.

![tar command](../images/Act11.png?classes=border,shadow)