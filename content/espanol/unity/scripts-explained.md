---
title: "Scripts Explained"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 4
---

Antes de comenzar a hacer que Nuvi se mueva, primero expliquemos la estructura de un script de Unity. Hay muchas formas de hacer que Nuvi se mueva dentro de Unity, y una de ellas es agregar un componente Script a Nuvi. Un componente Script es un componente que puedes crear por tu cuenta desde cero.

Un script vacío de Unity se verá así:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class EmptyScript : MonoBehaviour
{
   void Start()
   {
   }

   void Update()
   {
   }
}
```

Cada nuevo script tendrá las primeras 3 líneas que comienzan con `using`. Estas líneas son necesarias para que Unity pueda usar este script recién creado, por lo que generalmente las dejamos tal como están. La siguiente línea que comienza con `public class 'script_name'` es necesaria para que Unity acceda a este script específico.

{{< notice note >}}
¡Asegúrate de que el nombre del script coincida con 'script_name'! Si decides cambiar el nombre del script fuera del propio archivo, esto no actualiza la línea de código que contiene el nombre del script, así que asegúrate de volver y actualizarla, ¡de lo contrario el juego no se ejecutará!
{{< /notice >}}

Cada script tiene dos métodos predefinidos.

**void Start()**: Este método se llama solo una vez cuando el script se inicia. Usualmente se usa para inicializar variables que necesitaremos a lo largo del script.

**void Update()**: Este método se llama cada frame y suele usarse cuando queremos cambiar un comportamiento del juego.

Existe otro método que usaremos para hacer que Nuvi se mueva llamado `void FixedUpdate()`.

**void FixedUpdate()**: Este método se llama con menos frecuencia que Update(), pero se usa mejor cuando se trata con física para obtener movimientos más suaves, por ejemplo al usar Rigidbody.

Habrá otros métodos de la biblioteca de Unity que usaremos más adelante, ¡pero por ahora esto es todo lo que necesitas saber!