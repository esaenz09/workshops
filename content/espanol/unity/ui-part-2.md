---
title: "Making the UI: Part 2"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 13
---

## Pantalla final

A continuación, queremos crear una pantalla final que se mostrará una vez que Nuvi derrote a todos los alienígenas. Gran parte de este proceso será muy similar a cómo hiciste la Pantalla de Menú.

Debajo de "Canvas", crea "UI" → "Image" como hiciste para el menú inicial, y esta vez renómbralo a "EndScreen". Redimensiona al mismo tamaño que la Pantalla de Menú.

Crea "UI" → "Text" dentro de EndScreen, renómbralo a "EndMessage" y escribe el texto que prefieras — este mensaje se mostrará cuando Nuvi derrote a todos los alienígenas y el juego termine. En nuestro ejemplo dijimos: "¡Derrotaste a todos los alienígenas y ayudaste a Nuvi a salvar el Universo!"

Ahora queremos que el jugador pueda volver a jugar una vez que termine. Crea "UI" → "Button" dentro de EndScreen. Como hiciste con el StartButton, expande Button para encontrar el objeto Text y renómbralo a "ReplayButton". Edita el texto para que muestre "Volver a jugar".

Pero al igual que el botón de Inicio, hacer clic en este botón Replay todavía no hace nada. Crea otro script en tu carpeta Scripts y nómbralo "RestartScene".

Esta vez, en lugar de simplemente hacer desaparecer el EndScreen, queremos recargar todo: el menú inicial, a Nuvi y a los alienígenas que Nuvi derrotó. Copia y pega el código siguiente en tu script:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class RestartScene : MonoBehaviour
{
   public void restart()
   {
       Scene scene = SceneManager.GetActiveScene();
       SceneManager.LoadScene(scene.name);
   }
}
```

{{< notice tip >}}
Para recargar todo, usamos Scenes; pero para hacerlo, necesitas tener `using UnityEngine.SceneManagement;` declarado debajo de las 3 líneas habituales.
{{< /notice >}}

Arrastra y suelta este script desde la carpeta Scripts al inspector del ReplayButton. En la casilla `OnClick()`, haz clic en el "+" y, como hiciste con el StartButton, arrastra el objeto ReplayButton a la casilla que dice "None (Object)". Luego, busca y selecciona la función `restart()` del script RestartScene.