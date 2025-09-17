---
title: "Activity 7 - What's wrong with the file?"
description: "Use Linux commands to read the file without opening it"
date: 2022-09-23
difficulty: "Intermediate"
weight: 10
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/tgciAD4hbyU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡El malware puede ser peligroso! ¡No lo abras de inmediato! En su lugar, usemos la línea de comandos para echar un vistazo.
    </div>
</div>

{{% notice warning %}}
Para los archivos sobre los que no estamos seguros, debemos echarles un vistazo para no abrir accidentalmente un virus.
{{% /notice %}}

### ¿Cómo podemos ver las primeras líneas del archivo?

A veces solo necesitas mirar el comienzo de un archivo. El comando `head` muestra las primeras líneas de un archivo.  
El formato es: `head [filename]`

{{% notice tip %}}
Si añades la opción -n puedes indicar cuántas líneas quieres ver.  
El formato es: `head -n [# of lines] [filename]`
{{% /notice %}}

¡Intenta ver las primeras 5 líneas de `malware.sh`!

![head command](../images/Act7.1.png?classes=border,shadow)

### ¿Cómo podemos ver las últimas líneas del archivo?

A veces solo necesitas mirar el final del archivo. El comando `tail` muestra las últimas líneas de un archivo.  
El formato es: `tail [filename]`

{{% notice tip %}}
Si añades la opción -n puedes indicar cuántas líneas quieres ver.  
El formato es: `tail -n [# of lines] [filename]`
{{% /notice %}}

¡Intenta ver las últimas 5 líneas de `malware.sh`!

![tail command](../images/Act7.2.png?classes=border,shadow)

### ¿Cómo podemos ver todo el archivo?

A veces, mirar las primeras y las últimas líneas del archivo nos hace darnos cuenta de que necesitamos ver todo el archivo para entender qué está haciendo y qué deberíamos hacer al respecto.  
¡Veamos el contenido completo de `malware.sh`!

`cat` muestra el contenido de un archivo.  
El formato es: `cat [filename]`

{{% notice tip %}}
`less` y `more` son comandos similares a `cat`.

#### El comando more

`more` es un comando pensado para archivos más grandes. Muestra tantas líneas como sea posible y luego presionas Enter para ver la siguiente sección del archivo hasta llegar al final.  
El formato es: `more [filename]`

![more command](../images/Act7.3.png?classes=border,shadow)

#### El comando less

`less` es un comando útil para moverse hacia adelante y hacia atrás por secciones de un archivo. Funciona de forma similar a `more`, pero usas las flechas arriba y abajo para desplazarte entre secciones del archivo. Para salir, pulsa 'q'.  
El formato es: `less [filename]`

![less command](../images/Act7.4.png?classes=border,shadow)
{{% /notice %}}

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¿Qué crees que hace malware.sh? ¡Añádelo a tu informe!
    </div>
</div>