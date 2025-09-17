---
title: "Colliders"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 6
---

La razón por la que Nuvi se escapa es que no hay colliders que lo detengan.

{{< notice info >}}
Los colliders permiten que dos objetos se toquen.
{{< /notice >}}

Entonces, usemos colliders para añadir muros invisibles alrededor de nuestra arena. Ve a la ventana Hierarchy y haz clic derecho, luego elige "Create Empty". Nombra este objeto vacío "Walls".

Después, haz clic derecho en el objeto "Walls" que acabas de crear, y esta vez elige "3D Object -> Cube". Redimensiona el cubo en una forma rectangular para que cubra un lado de la pantalla como en la imagen de abajo:

![One invisible wall](../img/5_1stWall.png)

Luego, elimina el componente BoxCollider que el cubo trae por defecto, y añade un componente BoxCollider2D.

Haz lo mismo para crear 3 muros invisibles más que rodeen a Nuvi, como:

![Four invisible walls surrounding the arena](../img/5_all_walls.png)

Ahora ejecuta el juego y mira qué pasa. ...Ups, Nuvi todavía se escapa. Eso es porque Nuvi no tiene un Collider. ¡Para que dos objetos colisionen, ambos deben tener un Collider!

Así que, añade un componente BoxCollider2D a Nuvi. En ese componente, haz clic en "Edit Collider", y deberías ver un cuadro verde rodeando a Nuvi. Redimensiona ese cuadro para que quede ajustado alrededor de Nuvi.
Ejecuta el juego y verás que Nuvi ya no se escapa... pero ahora Nuvi empieza a girar cuando choca con una esquina de la arena. Para evitar esto, ve al componente Rigidbody2D de Nuvi, expande "Constraints" y marca "Freeze Rotation".

Para añadir un fondo y hacer que Nuvi funcione en el espacio exterior, arrastra el archivo png "background" desde la carpeta Drawings como hiciste con la imagen de Nuvi, y luego suéltalo en la Scene. Redimensiona la imagen de fondo; mirar la ventana Game te ayudará a hacerlo.

{{< notice tip >}}
Si Nuvi se oculta detrás de la imagen de fondo, ve al componente Sprite Renderer de Nuvi, expande "Additional Settings" y cambia el "Order in Layer" de Nuvi a 1 (o cualquier número mayor que 0).
{{< /notice >}}

Finalmente, ejecuta el juego otra vez y asegúrate de que todo se vea bien. Si es así, ¡felicidades! ¡Hemos ayudado con éxito a Nuvi a moverse por el espacio exterior!

![Nuvi on background image](../img/5_done.png)