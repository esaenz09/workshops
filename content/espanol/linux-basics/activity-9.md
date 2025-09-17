---
title: "Activity 9 - Remove the Bad File"
description: "Use Linux commands to remove the bad file and directory"
date: 2022-09-23
difficulty: "Intermediate"
weight: 12
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/mLsJXEIsadE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Entonces malware.sh es definitivamente un archivo malicioso dejado por los hackers. ¡Necesitamos eliminarlo y el directorio que lo contiene!
    </div>
</div>

## ¡Eliminar el archivo malicioso!

`rm` es un comando que elimina archivos.  
El formato es: `rm [filename]`.

{{% notice warning %}}
`rm` elimina el archivo permanentemente.
{{% /notice %}}

Elimina el archivo que hemos decidido que está causando nuestros problemas. ¿Cómo podemos comprobar que el archivo se eliminó por completo?

![rm command](../images/Act9.1.png?classes=border,shadow)

----

## ¿Y si necesitamos eliminar un directorio?

`rmdir` es un comando que puede eliminar un directorio vacío.  
El formato es: `rmdir [directoryName]`.

{{% notice warning %}}
`rmdir` elimina el directorio permanentemente.
{{% /notice %}}

¿Cómo puedes eliminar el directorio que contenía el archivo malicioso?

![rmdir command](../images/Act9.2.png?classes=border,shadow)

{{% notice warning %}}
Eliminar archivos puede ser una operación peligrosa, especialmente en Linux. Asegúrate de estar 100 % seguro de que el archivo que quieres eliminar es seguro de borrar. Al eliminar el archivo equivocado, podrías dañar accidentalmente tu equipo.
{{% /notice %}}

¿Recuerdas el comando para volver a crear el directorio que eliminamos?

![mkdir command](../images/Act9.3.png?classes=border,shadow)

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Ahora vamos a comprobar si sabemos un comando para restaurar el archivo secret-message.txt...
    </div>
</div>