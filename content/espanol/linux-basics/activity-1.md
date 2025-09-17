---
title: "Activity 1 - Determine User Account"
description: "Usa un comando de Linux para determinar qué usuario eres"
date: 2022-09-23
difficulty: "Intermediate"
weight: 4
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/XAtCQ9S1vSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Ahora estamos en la línea de comandos. Probemos un comando sencillo que nos muestre la cuenta de usuario.
    </div>
</div>

## ¿Qué son las cuentas de usuario?

Cada usuario en Linux tiene una cuenta de usuario. Estas se usan para identificar de forma única a cada usuario.

Por ejemplo, imagina que tú y tu amiga Nuvi comparten un ordenador. Tú y Nuvi podrían crear cuentas de usuario separadas para llevar un control de qué archivos pertenecen a cada uno y para asegurarse de que ninguno cambie algo importante por accidente.

## ¿Cómo averiguo qué cuenta estoy usando?

El comando de Linux `whoami` te dirá qué cuenta estás usando. ¡Pruébalo!

```
whoami
```

<!---![home directory](../images/01_whoami.png?classes=border,shadow) --->
<img src="../images/01_whoami.png" alt="home directory" style="width:600px;"/>

En nuestro ejemplo anterior, la salida del terminal es el nombre de nuestro usuario, `nuvi`.

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Ahora que comprobamos quiénes somos, a continuación averigüemos dónde estamos.
    </div>
</div>