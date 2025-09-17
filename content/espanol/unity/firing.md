---
title: "Firing"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 9
---

Ahora que el proyectil está todo listo, vamos a hacer que Nuvi dispare esos proyectiles. Crea un script llamado "FiringBehavior", luego copia y pega este código:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FiringBehavior : MonoBehaviour
{

   public Transform spawn_coor;        // dónde aparecerá el proyectil
   public float projectile_speed;          // qué tan rápido irá el proyectil

   public GameObject projectile_object;    // sprite de proyectil rojo

   // Start se llama antes de la primera actualización de frame
   void Start()
   {
       projectile_speed = 15f;
   }      

   // Update se llama una vez por frame
   void Update()
   {
       if(Input.GetButtonDown("Jump")) // la barra espaciadora generará el proyectil
       {

           Rigidbody2D rb = projectile.GetComponent<Rigidbody2D>();
           rb.AddForce(spawn_coor.up * projectile_speed, ForceMode2D.Impulse); // hace que el proyectil se mueva
       }
   }
}
```

Ahora mismo este script no funciona; necesitamos decirle al juego qué crear cuando se presione la barra espaciadora. Para hacerlo, añade `GameObject projectile = Instantiate(projectile_object, spawn_coor.position, spawn_coor.rotation);` encima de `Rigidbody2D rb = projectile.GetComponent<Rigidbody2D>();`. El método Instantiate indica qué crear, dónde crearlo y en qué dirección debe estar orientado.

Arrastra y suelta este script en el inspector de Nuvi. Si ejecutas el script ahora, notarás que no cambia nada. Esto se debe a que hay variables públicas que aún no han sido asignadas.
Ve al inspector de Nuvi y desplázate hasta el script Behavior. Observa que spawn_coor y projectile_object están vacíos. Para spawn_coor, arrastra y suelta el GameObject vacío que hiciste en la lección anterior que representa dónde aparecen los proyectiles. Para projectile_object, arrastra y suelta el prefab de proyectil que también hiciste en la lección anterior.

Además, ahora que Nuvi tiene todo lo que necesita para defenderse, ¡convirtamos también a Nuvi en un prefab!

Ejecuta el juego y fíjate en lo que ves. Logramos que Nuvi dispare proyectiles, ¡pero estos proyectiles no pueden hacer nada! En las próximas lecciones, aprenderás cómo hacer que interactúen con otros objetos.