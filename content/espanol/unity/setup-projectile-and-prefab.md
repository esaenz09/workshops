---
title: "Setting up the Projectile and Making it a Prefab"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 8
---

¡Oh no! ¡El alienígena rosa está atacando ahora! Está enfadado porque Nuvi lo atropelló. Vamos a equipar a Nuvi con un mecanismo de autodefensa.

Después de seleccionar a Nuvi en la jerarquía, haz clic derecho y selecciona "Create Empty", lo que crea un GameObject vacío con solo un componente Transform.

{{< notice tip >}}
Para poder ver dónde está nuestro objeto vacío, ¡asegúrate de estar en la herramienta Move! Deberías ver dos flechas que se cruzan; donde se cruzan es donde se encuentra nuestro GameObject vacío.
{{< /notice >}}

Este componente Transform representará desde dónde va a generarse el proyectil. Usando la herramienta Move, alineemos el Transform para que quede frente al vientre prominente de Nuvi. Rota el Transform usando la herramienta Rotate para crear una imagen similar a la de abajo:

<img src="../img/7_projectileSpawn.png" alt="Reposition and rotate projectile spawn Transform so it is in front of Nuvi" width="400"/>

Ahora, en la carpeta Assets dentro de la ventana Project, localiza el png "projectile" en la carpeta Drawings. Arrastra y suelta el projectile en la jerarquía. Redimensiona el projectile para que sea más pequeño que Nuvi. Asegúrate de añadir un BoxCollider2D y un RigidBody2D con el gravity scale ajustado a 0.

{{< notice tip >}}
Si la imagen del projectile no se muestra, intenta ir al componente Sprite Renderer y aumentar el "Order in Layer", como hiciste con Nuvi cuando añadimos el fondo.
{{< /notice >}}

## Prefabs

Dado que vamos a disparar múltiples proyectiles, sería más fácil convertir los proyectiles en un prefab. Un prefab es una versión predefinida de un objeto de la que puedes hacer muchas copias simplemente arrastrándola a la escena. Si haces algún cambio en el prefab, ese cambio afectará a todas las copias de ese prefab. No tienes que entrar en cada copia y cambiar todo manualmente.

Primero, creemos una carpeta "Prefabs" bajo Assets en la ventana Project. Luego, para convertir el projectile en un prefab, simplemente arrastra el projectile desde la jerarquía a la carpeta Prefabs.

{{< notice note >}}
Ten en cuenta que el texto "projectile" y el cubo vacío junto a él se volvieron azules en la jerarquía.
{{< /notice >}}

Ahora que el projectile está guardado para uso futuro, podemos eliminar el projectile de la jerarquía. Para hacerlo, simplemente haz clic derecho sobre el projectile y elige "Delete".