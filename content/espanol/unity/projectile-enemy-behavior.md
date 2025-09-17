---
title: "Projectile/Enemy Behavior"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 11
---

## Comportamiento del proyectil

Ahora que sabemos cómo funcionan los triggers y las tags, ¡vamos a configurar el comportamiento del proyectil! Crea un nuevo script dentro de la carpeta Scripts llamado "ProjectileBehavior". Luego arrástralo al inspector del proyectil desde la carpeta Prefabs y abre el script. Elimina las funciones `Start()` y `Update()` y reemplázalas con esto:

```csharp
void OnTriggerEnter2D(Collider2D collision)
{
    if(collision.gameObject.tag != "")  // destruir el proyectil si choca con cualquier cosa que no sea el jugador
    {
      // hacer que el proyectil desaparezca

    }
}
```

En esta función queremos destruir el proyectil si colisiona con cualquier cosa que no sea el jugador. ¿Qué crees que deberíamos añadir dentro de las comillas? Dentro del cuerpo de la función, ¿qué deberíamos poner para hacer que el proyectil desaparezca?

{{< notice tip >}}
¡Podemos usar la etiqueta de Nuvi en la sentencia if!
{{< /notice >}}

{{< notice tip >}}
- Destroy(???) destruirá el gameObject especificado por ???
- gameObject es una variable que se refiere al objeto al que está adjunto este script
{{< /notice >}}

{{< expand "¡Haz clic aquí para ver la respuesta!" >}}
```csharp
   void OnTriggerEnter2D(Collider2D collision)
   {
       if(collision.gameObject.tag != "Player")  // destruir el proyectil si choca con cualquier cosa que no sea el jugador
       {
		       // hacer que el proyectil desaparezca
           Destroy(gameObject);
       }
   }
```
{{< /expand >}}

---

## Comportamiento del enemigo

¡Ahora probemos ejecutando el juego! Si lo hicimos correctamente, el proyectil debería desaparecer al contacto cuando toque cualquier cosa que no sea Nuvi. Sin embargo, cuando disparamos al enemigo, fíjate cómo el proyectil desaparece, pero el enemigo no. Para solucionar este problema, debemos crear un script similar que se centre en el comportamiento del enemigo.

Para ello, crea un nuevo script en la carpeta Scripts llamado "EnemyBehavior" y adjúntalo al inspector de Alien_pink. De forma similar a como hicimos el script "ProjectileBehavior", elimina las funciones `Start()` y `Update()` y añade esto:

```csharp
void OnTriggerEnter2D(Collider2D collision)
{
    if(collision.gameObject.tag == "") // destruir el enemigo si choca con un proyectil
    {
        // hacer que el enemigo desaparezca

    }
}
```

En esta función queremos destruir el enemigo si colisiona con un proyectil. ¿Qué crees que deberíamos añadir? ¿Qué deberíamos poner en el cuerpo de la función para hacer que el proyectil desaparezca?

{{< notice tip >}}
¡Podemos usar la tag del proyectil en la sentencia if!
{{< /notice >}}

{{< notice tip >}}
¡Es lo mismo que en el script "ProjectileBehavior"!
{{< /notice >}}

{{< expand "¡Haz clic aquí para ver la respuesta!" >}}
```csharp
   void OnTriggerEnter2D(Collider2D collision)
   {
       if(collision.gameObject.tag == "Projectile") // destruir el enemigo si choca con un proyectil
       {
           Destroy(gameObject);
       }
   }
```
{{< /expand >}}

---

Ahora que hemos añadido estos dos scripts, ¡probemos ejecutar el juego! Comprueba lo siguiente:
1. los proyectiles desaparecen cuando golpean al alien
2. los proyectiles desaparecen cuando golpean las paredes invisibles
3. el alien desaparece cuando es alcanzado por un proyectil

Aprovechando, convirtamos también al alien_pink en un prefab. Sin embargo, en lugar de eliminar el alien después de convertirlo en prefab, añadamos dos aliens más a la escena. Simplemente arrastra el alien a la jerarquía y reubícalos como quieras usando la Move tool.

---

Hagamos una pausa y veamos lo que lograste. Pudiste hacer que Nuvi se mueva en 8 direcciones, darle la capacidad de disparar proyectiles, y hacer que los enemigos y los proyectiles desaparezcan al colisionar. ¡Date una palmada en la espalda; lograste mucho! ¡Sigamos adelante! ¡Casi hemos terminado!