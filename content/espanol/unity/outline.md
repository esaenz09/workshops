---
title: "Piecing it All Together"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 14
---

Ahora que tenemos toda la interfaz de usuario lista, queremos que el juego funcione como pretendemos. En este momento, cuando simulamos el juego jugable, podemos mover a Nuvi, pero la pantalla final ya aparece.
Para arreglar esto, tendremos un script que dictará cómo debe desarrollarse el juego. Bajo la carpeta Scripts en la ventana de Projects, crea un nuevo script llamado "Outline". Arrastra este script al inspector de la "Main Camera", que podemos ubicar en el hierarchy.

Antes de agregar cualquier cosa al script "Outline", primero preparemos algunas cosas. Si ejecutáramos el juego ahora, todavía podríamos mover a Nuvi y disparar a los enemigos rosas a pesar de que la UI aparece. Arreglemos eso configurando puntos de aparición (spawn points).
Haz "Create Empty" en la ventana de hierarchy y renómbralo a "SpawnPoints". Luego, crea cuatro Transforms más bajo "SpawnPoints" y renómbralos "EnemyLoc1", "EnemyLoc2", "EnemyLoc3", y "PlayerLoc". Reposiciónalos usando la herramienta Move de manera que estén justo sobre los enemigos y el jugador, así:

<img src="../img/13_enemyspawn.png" alt="Reposition spawn point for enemy" width="400"/>
<img src="../img/13_playerspawn.png" alt="Reposition spawn point for Nuvi" width="400"/>

{{< notice tip >}}
Asegúrate de que los Transforms estén en el mismo eje Z que Nuvi. ¡De lo contrario, podrían no aparecer!
{{< /notice >}}

Ahora que tenemos todo configurado, abramos el script outline y copia y pega este código:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;


public class Outline : MonoBehaviour
{

   public Slider num_of_enemies;


   private Transform location;

   public GameObject opening_screen;
   public GameObject winner_screen;
   public GameObject enemy1;
   public GameObject player1;

   private bool is_generated;


   // Start es llamado antes de la primera actualización de fotograma
   void Start()
   {

       is_generated = false;

   }

   // Update es llamado una vez por fotograma
   void Update()
   {
       if(is_generated == false)
       {
           if (opening_screen.activeSelf == false)
           {
               generate();
               is_generated = true;
               enemies_left = (int) num_of_enemies.value;
           }
       }

       if(enemies_left == 0)
       {
           showEndScreen();
       }
   }

   private void generate()
   {
       for(int x = 1; x <= ; x++) // por cada número de enemigos elegido con el slider
       {
           location = positions[x];    // como es un arreglo, toma el Transform del índice x
           GameObject enemy = Instantiate(enemy1, location);   // instancia al enemigo en la ubicación elegida
       }
       location = positions[0];
       GameObject player = Instantiate(player1, location);
   }

   private void showEndScreen()
   {
       winner_screen.SetActive(true);
   }
}
```

A este código le faltan unas líneas para que funcione correctamente. Rellenémoslas, ¿de acuerdo?

Si intentáramos ejecutar el juego ahora, no nos dejaría. Una razón es que usamos un objeto UI en el script. Para acceder a él, necesitamos importar el namespace de UI. Para ello, añade `using UnityEngine.UI;` al inicio del script debajo de `using UnityEngine;`.

A continuación, queremos almacenar las posiciones de spawn que creamos. ¿Qué estructura de datos crees que es la mejor para guardarlas? ¡Si pensaste en arreglos (arrays), estás en lo correcto! Añade la línea `public Transform[] positions;` justo encima de `private Transform location;`. Esto nos permitirá almacenar todos los puntos de spawn sin tener que crear cuatro variables individuales.

Un problema que tuvimos fue que la pantalla final aparecía pese a estar al inicio del juego. Si prestaste atención a los dos scripts anteriores para el Menu y la pantalla de fin, puede que tengas una idea de cómo arreglarlo. Similar a cómo pusimos la pantalla del Menu en false, necesitamos poner la pantalla final en false. Para ello, añade `winner_screen.SetActive(false);` dentro del método `Start()`.

La adición final que necesitamos para que el script funcione está en la función `generate()`. Dentro del bucle for, necesitamos una forma de tomar el número que el jugador eligió en el slider dentro de la pantalla del Menu. Como nos referiremos al slider como num_of_enemies, simplemente necesitamos añadir `num_of_enemies.value` justo después del `<` y antes del `;` en el for.

Ahora, ve al inspector de la Main Camera y localiza el script Outline. Observa que hay muchas variables vacías que necesitamos completar. Primero, arrastra el slider num_enemies desde el hierarchy a la variable "Num_of_enemies". Para "Positions", elige "4". Arrastra las ubicaciones de spawn en este orden empezando desde Element 0: PlayerLoc → EnemyLoc2 → EnemyLoc1 → EnemyLoc3. Luego, arrastra el GameObject Menu desde el hierarchy a la variable "Opening_screen" y el GameObject EndScreen a la variable "Winner_screen". A continuación, desde la carpeta Prefabs en la ventana de Project, arrastra el prefab "enemy1" a la variable "Enemy 1" y el prefab "Nuvi" a la variable "Player 1".

Luego, necesitamos una forma de saber cuándo los enemigos son derrotados, para que la pantalla final aparezca cuando no queden enemigos. Para ello, llevamos un conteo de cuántos enemigos hay, y este conteo debe disminuir cuando un enemigo es derrotado. En el script "Outline" añade `public int enemies_left;`. Por ahora añade `enemies_left = -1;` en el método `Start()`. Ahora, pensemos cuándo se derrota al enemigo. ¿En qué script destruimos al enemigo? Si pensaste en el script "EnemyBehavior", ¡correcto! Abre el script "EnemyBehavior" y añade este código sobre el método `OnCollisionEnter2D()`:

```csharp
  GameObject cam;
  private Outline outline;

  void Start()
  {
      cam = GameObject.Find("Main Camera");
      outline = cam.GetComponent<Outline>();
  }
```

La primera línea en el método `Start()` asigna la variable "cam" como el GameObject "Main Camera". La segunda línea obtiene el script Outline desde "cam" y lo asigna a la variable "outline". A continuación, añade `outline.enemies_left--;` debajo de `Destroy(gameObject);`. Esto restará 1 a la variable "enemies_left" en el script "Outline".

Finalmente, todo lo que necesitamos hacer es eliminar todos los enemigos y a Nuvi de la ventana Scene. Esto es porque queremos que aparezcan (spawn) solo cuando presionemos el botón de inicio. Haz clic derecho sobre ellos en el hierarchy y selecciona eliminar.

Uf... fue bastante, ¿no? ¡Ahora intenta ejecutar tu juego! Si todo está bien, ¡felicidades! ¡Hiciste tu primer juego! Pero aún no has terminado. Intentemos exportar tu juego para que puedas compartirlo con otros.