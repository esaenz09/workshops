---
title: "Triggers and Tags"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 10
---

## Triggers

Ahora, hagamos una pausa y pensemos cómo queremos que funcione nuestro proyectil. Un proyectil será disparado y, cuando golpee a un enemigo, desaparecerá. ...Eso no es realmente física, ¿verdad? La física no puede hacer que un objeto desaparezca en el aire, así que este comportamiento de desaparecer tendrá que ser algo personalizado que añadamos al proyectil mediante un script. El comportamiento de desaparecer ocurrirá cuando el proyectil toque a un enemigo.

Hacemos eso convirtiendo este proyectil en un trigger. Ve al componente BoxCollider2D dentro del inspector del proyectil que añadiste, y marca la casilla "IsTrigger". Un trigger te permitirá saber que tocó algo, así que en tu script podrás comprobar si esa interacción ocurrió y entonces hacer que ocurra ese comportamiento personalizado de desaparecer.

<img src="../img/9_isTrigger.png" alt="Check IsTrigger box" width="400"/>

Ten en cuenta que, porque este proyectil es un trigger, ya no funcionará mediante la física. A menos que añadas un script para hacerlo desaparecer, va a atravesar objetos, incluidas las paredes invisibles que añadiste antes.

{{< notice info >}}
Convertir un Collider en un Trigger desactiva las reacciones físicas, pero ese objeto aún puede notificarte cuando ocurre una colisión.
{{< /notice >}}

## Tags

Antes de ponernos a crear el siguiente script, debemos hablar de una cosa más: las tags. Las tags se usan para identificar fácilmente los GameObjects dentro de Unity. Las utilizaremos al crear los siguientes dos scripts. Primero, debemos configurar las tags dentro de nuestro juego.

Justo en la parte superior de la ventana del inspector de Nuvi, localiza el desplegable "Tag". En este momento, debería decir "Untagged". Abre el menú desplegable y selecciona "Player". Ahora, Nuvi tiene una tag "Player" que podemos localizar fácilmente. Repite esto tanto para el proyectil como para el enemigo. Si quieres crear una nueva tag, selecciona "Add Tag…" en el menú desplegable y pulsa el signo "+". Luego nombra tus nuevas tags como "Projectile" y "Enemy" y guarda.