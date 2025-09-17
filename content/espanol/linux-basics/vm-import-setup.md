---
title: "Using Virtual Machines Part 2"
description: "Continuando la guía introductoria para usar máquinas virtuales"
date: 2022-09-23
difficulty: "Intermedio"
weight: 2
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/ffcyyJXEhwY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Excelente trabajo preparando el entorno anfitrión! Ahora carguemos la imagen del equipo comprometido como una máquina virtual.
    </div>
</div>

## ¿Qué es una imagen?

`Images` vienen en una variedad de tipos. Tenemos fotografías, que son imágenes. Las imágenes de ordenador son muy similares. Ambas son copias de algo en un punto específico en el tiempo. Trabajaremos con una copia de un equipo que se ha comportado de forma extraña. ¡No te preocupes, esto no dañará tu equipo! Recuerda que el SO estará en una `sandbox`, lo que significa que no puede afectar a tu equipo.

## Configuración de Kali Linux

### Descargando la imagen

`OS images` facilitan enviar copias exactas de equipos.  
VirtualBox usa la extensión de archivo `.ova` para sus imágenes de máquina. Esto es similar a cómo guardas documentos como un archivo `.docx` y fotografías como `.png`.

¡Descarguemos nuestra copia del equipo! Haz clic en el enlace de abajo para descargar.  
La mayoría de las imágenes de SO son grandes (~8 GB), pero la nuestra es solo ~3 GB. La descarga aún puede tardar unos minutos.

<a class="my-2 mx-4 btn btn-info" href="https://nuevofoundation-my.sharepoint.com/:f:/g/personal/beatris_mendezgandica_nuevofoundation_org/EqwR5wQyp9xEpYoP524regQB6rnwgyJBMULhuGIzyMj_4w?e=yg6rFv" target="_blank">
Download link
</a>

### Importando la máquina virtual

¡Ahora que tienes la imagen de la máquina descargada, es hora de configurarla!

#### Paso 1

En la aplicación VirtualBox, podemos _importar_ nuestras imágenes. ¡Hagamos clic en el botón "Import" para empezar!

![virtual box import button](../images/import-01.PNG?classes=border,shadow)

#### Paso 2

El appliance que queremos importar será el archivo `.ova` que descargaste anteriormente. Adelante, haz clic en la pequeña carpeta con un símbolo de caret verde. Esto abrirá una ventana para que puedas localizar y seleccionar el archivo `.ova`.

![virtual box import screen](../images/import-02.PNG?classes=border,shadow)

#### Paso 3

Ahora que seleccionaste el archivo de imagen .ova. Haz clic en "Open". Luego haz clic en "Next" en la pantalla "Appliance to Import".

![virtual box import screen](../images/import-03.PNG?classes=border,shadow)

#### Paso 4

¡El último paso! En el campo "Name", siéntete libre de darle un nombre nuevo. ¡Es tu propia VM! Asegúrate de que la opción "USB Controller" **no** esté seleccionada. Asegúrate de desmarcarla. A continuación, para la MAC Address Policy, es buena idea verificar que diga "Generate new MAC addresses for all network adapters". Finalmente, haz clic en "Import"!

![virtual box import screen](../images/import-05.PNG?classes=border,shadow)

**Nota:** aparecerá un cuadro emergente con el tiempo necesario para completar la importación.  
Normalmente esto toma unos 5 minutos, pero puede tardar un poco más dependiendo de tu equipo.

![virtual box import screen](../images/import-06.JPG?classes=border,shadow)

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Ahora podemos iniciar la máquina infectada y comenzar con nuestras investigaciones!
    </div>
</div>