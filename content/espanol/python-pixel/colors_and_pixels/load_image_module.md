---
title: "Import an image module"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 1
--- 

### Configurar el proyecto

Para hacer cosas divertidas con imágenes, necesitamos desbloquear algunas funciones útiles. Para obtener estas funciones, tenemos que importar un módulo. En este caso, si importamos el módulo <b>Pillow</b>, podemos usar algunas funciones que nos ayudarán a modificar imágenes.

Primero, eliminemos todo el contenido del archivo main.py. Luego, añade las siguientes sentencias:

<pre>
    <font color="blue">from</font> PIL <font color="blue">import</font> Image
    <font color="blue">from</font> PIL <font color="blue">import</font> ImageFilter
</pre>


Al ejecutar, deberías ver que el módulo se instala en la consola:

![alt text](../../media/installed_module.png "image of what you should see when you successfully install the module")

Si ves lo anterior, ¡significa que has importado con éxito un módulo! Si tienes problemas, pide ayuda antes de continuar.

{{% notice note %}}

Si tienes curiosidad por ver qué funciones ofrece el módulo Pillow Image, puedes encontrar información aquí: https://pillow.readthedocs.io/en/latest/handbook/index.html

{{% /notice %}}