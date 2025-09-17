---
title: "Activity 5 - Secure User Permissions"
description: "Use a Linux command to secure your files"
date: 2022-09-23
difficulty: "Intermediate"
weight: 8
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/D5Y6LH0mBi0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="A photo of Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Oh no! ¡Algunos de nuestros archivos podrían haber sido modificados! Aseguremos nuestras notas, file1. ¡No queremos que un hacker las manipule!
    </div>
</div>

### ¿Cómo limitamos el acceso a nuestros archivos?

¡Dando a los usuarios "permisos" sobre los archivos!

Los permisos son una forma para que el ordenador determine quién tiene acceso a los archivos y qué puede hacer con ellos.

En Linux, hay tres tipos comunes de acceso a un archivo que un usuario puede solicitar: "read", "write" o "execute".

{{% notice note %}}

El acceso "Read" significa que un usuario puede abrir y leer un archivo. El acceso "Read" a menudo se representa con el símbolo `r`.

El acceso "Write" significa que un usuario puede abrir y escribir en un archivo. Esto incluye renombrar y mover un archivo a una ubicación diferente en el sistema de archivos. El acceso "Write" a menudo se representa con el símbolo `w`.

El acceso "Execute" significa que un usuario puede intentar ejecutar el archivo como un programa. El acceso "Execute" a menudo se representa con el símbolo `x`.

{{% /notice %}}

### ¿Pero cómo sabemos qué tan seguros están nuestros archivos?

¿Hay un comando que hayamos aprendido hasta ahora que pueda mostrarnos qué tan seguros están nuestros archivos?  
¡Siéntete libre de volver atrás si lo necesitas!

![ls -l command](../images/Act5.1.png?classes=border,shadow)

Deberíamos seguir usando ese comando para comprobar si cambiamos los permisos como esperábamos.

---

### ¿Entonces, cómo aseguramos los archivos con permisos?

```
chmod u=rwx g=rx o=x file1
```

`chmod` es un comando usado para modificar los permisos de tus archivos (significa "Change Mode") para los siguientes 3 distintos grupos de usuarios:

- el <b>u</b>ser y propietario del archivo
- el <b>g</b>roup y los miembros del grupo de personas con acceso al archivo
- el <b>o</b>thers u cualquier otra persona

A estos grupos se les pueden asignar permisos para hacer lo siguiente:

- <b>r</b>ead
- <b>w</b>rite
- e<b>x</b>ecute.

---

### ¡Inténtalo tú!

Ahora, intentemos cambiar los permisos de nuestros archivos. Queremos que cualquier persona que esté fuera de nuestro grupo y que no seamos nosotros no pueda acceder a `file1`. ¿Cómo lo haríamos?

![chmod command](../images/Act5.2.png?classes=border,shadow)

#### Dato curioso: ¡Atajo!

`chmod` también puede usarse con comandos numéricos simples. Estos comandos se escriben así:

```
chmod 751 [insert filename]
```

Los valores pueden entenderse como dar a los usuarios permiso para leer, escribir y ejecutar.  
¿Qué permisos otorgan los otros dos valores?

| Number |        Significado         |
| :----: | :------------------------: |
|   7    | read + write + execute     |
|   6    |      read + write          |
|   5    |     read + execute         |
|   4    |          read              |
|   3    |    execute + write         |
|   2    |         write              |
|   1    |        execute             |
|   0    |     no permission          |

; manteniéndolo claro para principiantes.  
Preserva los términos técnicos, la sintaxis de código y el formato. Solo traduce los comentarios que expliquen conceptos.