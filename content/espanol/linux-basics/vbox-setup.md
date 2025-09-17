---
title: "Using Virtual Machines Part 1"
description: "An introductory guide to using virtual machines"
date: 2022-09-23
difficulty: "Intermediate"
weight: 1
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/zoutwedSLKI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Le estamos proporcionando una copia del equipo hackeado como una virtual machine para que pueda ayudarnos.
    </div>
</div>

{{% notice info %}}

### ¿Qué es una virtual machine?

Una **virtual machine** (comúnmente llamada VM) es un archivo de ordenador (llamado `image`) que se comporta como un ordenador real.  
En otras palabras, es un ordenador dentro de otro ordenador. Se ejecuta en una ventana, como cualquier otro programa.  
Esto te proporciona la misma experiencia en una VM que tendrías en un ordenador normal.

La VM está `sandboxed` del resto del sistema, lo que significa que el software dentro de una VM no puede afectar al propio equipo.  
Esto genera un entorno ideal para probar otros sistemas operativos, acceder a datos infectados por virus y crear nuevo software o aplicaciones.
{{% /notice %}}

## ¿Qué es VirtualBox?

VirtualBox es un software de virtualización, también llamado `hypervisor`. Permite que tu equipo aloje virtual machines.

## Descarga de VirtualBox

Puedes descargar VirtualBox usando este enlace:

<a class="my-2 mx-4 btn btn-info" target="_blank" href="https://www.virtualbox.org/wiki/Downloads">
Enlace de descarga
</a>

Si estás usando Windows: selecciona "Windows hosts"  
Si estás usando macOS: selecciona "OS X hosts"  
Si usas otro sistema, recomendamos utilizar Windows o macOS para este taller. Cualquier otra opción está fuera del alcance de este taller.

![virtual box download page](../images/vbox-dlpage-update.PNG?classes=border,shadow)

A continuación, ejecuta el instalador que acabas de descargar.

¡Las opciones predeterminadas serán suficientes para hoy! Sigue haciendo clic en "Next" en el instalador.

Ten en cuenta que hay algunas selecciones de opciones en la tercera página.
![virtual box install options](../images/vbox-install-03.PNG?classes=border,shadow)

Si ves esta advertencia, no te preocupes, esto es esperado.
![virtual box network warning](../images/vbox-install-04.PNG?classes=border,shadow)

Una vez que llegues a esta página haz clic en "Install" para terminar la configuración.
![virtual box install](../images/vbox-install-05.PNG?classes=border,shadow)

Por último, selecciona la casilla para iniciar VirtualBox después de que termine de instalarse.
![virtual box launch after install](../images/vbox-install-06.PNG?classes=border,shadow)

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Sí! Hemos terminado la instalación de VirtualBox. Ya estamos listos para empezar a usarlo.
    </div>
</div>