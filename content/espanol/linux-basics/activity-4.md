---
title: "Activity 4 - Note Taking Practice"
description: "Use Linux commands to create new directory"
date: 2022-09-23
difficulty: "Intermediate"
weight: 7
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/h9qokQeLREI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        Como ingeniero de ciberseguridad, es importante tomar muchas notas. Estas son útiles para futuras referencias para entender cómo ocurrió el ataque. ¡Organicemos nuestro espacio de trabajo!
    </div>
</div>

### ¿Qué pasa si quiero crear un nuevo directorio?

Para practicar la creación de un nuevo directorio, utiliza el comando `mkdir` (que significa "Make Directory") en el siguiente formato: `mkdir nombre_del_nuevo_directorio`.

Creamos un directorio llamado `files` escribiendo el siguiente comando:

```
mkdir files
```

<!---![ls-l command](../images/04_mkdir.PNG?classes=border,shadow) --->
<img src="../images/04_mkdir.PNG" alt="mkdir command" style="width:600px;"/>

Como puedes ver, ahora cuando se ejecuta `ls -l`, aparece un directorio adicional llamado `files`.

### ¿Qué puedes hacer con estos archivos?

Un ejemplo de cómo puedes manipular un archivo o directorio es moviéndolo a otra ubicación. Esto se logra con el comando de mover, `mv`. Practiquemos moviendo el directorio `Music` dentro del directorio `Documents`.

Escribe el comando que aparece a continuación:

```
mv Music/ Documents/
```

Ahora escribe `ls -l` una vez más y observa la salida.

![ls-l command](../images/04_mv_music_dir.png?classes=border,shadow)

Deberías ver que el directorio `Music` ya no aparece, porque fue movido dentro del directorio `Documents`.

{{% notice tip %}}
Podemos ver que se movió dentro de `Documents` usando el comando `ls` con la ruta del directorio añadida.

```
ls -l Documents/
```

{{% /notice %}}

Practiquemos `mv` una vez más moviéndolo de vuelta.

Inténtalo:

```
mv Documents/Music/ .
```

Esto mueve el directorio `Music` desde `Documents` a nuestro directorio actual, denotado por `.` El punto se usa en los comandos para denotar el directorio actual. Escribir `ls -l` una vez más muestra que `Music` ha regresado a este directorio.

<img src="../images/../images/03_ls-l.png" height="500" alt="ls -l command"/>

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Buen trabajo! Ahora sabes cómo mover archivos. Usaremos este conocimiento pronto para recuperarnos del ataque.
    </div>
</div>

### ¿Qué pasa si quiero crear un nuevo archivo?

Para crear un archivo podemos usar el comando `touch`. El comando touch crea un archivo vacío sin datos.

Prueba el siguiente comando para crear un archivo llamado `file1`:

```
touch file1
```

<!---![ls-l command](../images/04_touch.PNG?classes=border,shadow) --->
<img src="../images/04_touch.PNG" alt="touch command" style="width:600px;"/>

Ahora cuando escribimos `ls -l` podemos ver que el archivo ha sido creado.

### ¿Qué pasa si quiero añadir datos al archivo?

Un archivo vacío no tiene mucha utilidad, así que añadamos algunos datos, por ejemplo nuestro nombre.
Para abrir el archivo y editarlo usaremos el comando `vim`. Vim es un editor que nos permite añadir, eliminar y cambiar los datos en un archivo.

Escribe el siguiente comando para editar file1:

```
vim file1
```

<!---![ls-l command](../images/04_vim.PNG?classes=border,shadow) --->
<img src="../images/../images/04_vim.PNG" height="500" alt="vim command"/>

Ahora estamos en el editor Vim. Presiona `i` para entrar en el modo de inserción. Escribe `nuvi` y presiona `esc` para salir del modo de inserción. Finalmente escribe `:wq` y presiona enter. Los dos puntos indican a Vim que estás entrando un comando. La `w` y la `q` indican que quieres guardar los cambios y salir.

{{% notice warning %}}
Para salir de `vim`, presiona `esc` y luego escribe `:wq`. ¡Necesitarás esto cada vez que abras `vim`!
{{% /notice %}}

![ls-l command](../images/04_vim_after.PNG?classes=border,shadow)

<img src="../images/04_vim_after.PNG" alt="vim after" style="width:600px;"/>

Una vez más, escribe `ls -l` y puedes ver que file1 ahora tiene 5 bytes de contenido, en lugar de 0 cuando estaba en blanco.

{{% notice note %}}

Definición: Un <b>byte</b> es una unidad de medida para datos. En el nivel más bajo, los ordenadores usan lo que se conoce como un "bit", que es una unidad de datos cuyo valor solo puede ser "0" o "1", para representar información. Un byte es una colección de 8 bits.

{{% /notice %}}

Una última cosa. Movamos nuestro nuevo archivo a nuestro nuevo directorio.

Escribe el siguiente comando:

```
mv file1 files
```

<div style="margin: 1rem;padding: 2rem 2rem;text-align: center;">
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;">
        <img src="../images/nuvi.PNG?" alt="Uma foto de Nuvi" width="180" height="180" />
    </div>
    <div style="display: inline-block;padding: 1rem 1rem;vertical-align: middle;width:50%;border:5px solid #2980b9;border-radius:10px;font-weight: bold;">
        ¡Felicidades! Has creado, editado y movido tu primer archivo. ¡Ahora aseguraremos nuestro sistema!
    </div>
</div>