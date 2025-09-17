---
title: "Activity 8 - What's different?"
description: "Use Linux commands to compare files"
date: 2022-09-23
difficulty: "Intermediate"
weight: 11
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/fAI1kyAoVTA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Echemos un vistazo al mensaje secreto para asegurarnos de que este extraño archivo `malware.sh` no haya hecho nada!
    </div>
</div>

## Diferencias

¿Conocemos algún comando que nos ayude a encontrar la ubicación del archivo `secret-message.txt`?

![find command](../images/Act8.1.png?classes=border,shadow)

Entremos en ese directorio y busquemos la cita "Do. Or do not. There is no try." de antes. ¿Recuerdas qué comando puede ayudarnos a comprobarlo?

![grep command](../images/Act8.2.png?classes=border,shadow)

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Este archivo normalmente contiene citas buenas y divertidas, pero parece que tiene muchos cambios. ¿Deberíamos compararlo con una versión conocida como buena?
    </div>
</div>

Veamos si hay copias de seguridad del mensaje secreto dentro de su directorio. Ve al directorio Document y prueba:

```
ls -la
```

{{% notice tip %}}
La opción `-a` muestra todas las entradas, incluidos los archivos ocultos.
{{% /notice %}}

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¿Encontraste nuevos archivos? ¡Toma nota de los cambios!
    </div>
</div>

## Compara el archivo secret-message.txt con el archivo de respaldo

`diff` es un comando que se usa para comparar dos archivos y ver qué se ha añadido, cambiado o eliminado.  
El formato es: `diff [filename] [Filename of Comparison File]`

{{% notice info %}}
Dato curioso: ejecutar `diff --help` mostrará información sobre cómo usar la herramienta `diff`, incluidas las opciones disponibles.
{{% /notice %}}

Revisa las diferencias entre los dos archivos. ¿Cuántas diferencias encontraste? ¡Anótalo en el archivo que creaste!

{{% notice tip %}}

### Una mejor manera de ver las diferencias

`vimdiff` es un comando que abre una ventana con los archivos en paneles separados resaltando las diferencias.

Prueba `vimdiff` para visualizar mejor las diferencias entre los archivos.
{{% /notice %}}