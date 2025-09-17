---
title: "Making the UI: Part 1"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 12
---

## Pantalla del menú

¡Ya casi terminamos! Para completar este juego, necesitamos hacer dos cosas más: añadir una UI y un script Outline para ensamblarlo todo. Empecemos con la UI.

Haz clic derecho en la ventana de la jerarquía y, en lugar de seleccionar "Create Empty", queremos crear un canvas. Busca "UI" → "Canvas". Aquí estarán todos nuestros elementos de UI.

Bajo "Canvas", queremos crear "UI" → "Image". Renombra "Image" a "Menu". Esta será nuestra pantalla de menú. En el inspector del Menu, ajusta el ancho y la altura a 400 y 300 respectivamente.
Luego queremos anclar la pantalla Menu al centro. De esta manera, incluso si cambia el tamaño de la ventana, la pantalla del menú permanecerá en el centro. Para hacerlo, haz clic en los cuadrados en la esquina superior izquierda bajo Rect Transform en el inspector del Menu.

<img src="../img/11_anchors.png" alt="Anchor tool" width="400"/>

Mantén pulsadas las teclas Shift y Alt (en Mac, mantén Option en lugar de Alt) y selecciona el centro/medio en los Anchor presets. Esto establecerá el pivot del Menu a 0 mientras coloca la posición en el centro/medio.

Ahora, bajo Menu, crea un "UI" → "Text" y renómbralo a "Title". Cambia el texto por el nombre que quieras darle a tu juego en Text dentro del inspector "Title". ¡Deja fluir tu creatividad! También puedes cambiar el tamaño de la fuente a lo que prefieras.

{{< notice tip >}}
Si el texto desaparece, usa la herramienta rect (Rect tool) para aumentar el tamaño del cuadro de texto en la ventana Scene.
{{< /notice >}}

Cambia el anchor preset a top/center. Juega con el valor Pos Y hasta que la ubicación del texto te guste.

Crea otro "UI" → "Text" bajo Menu en la jerarquía y renómbralo a "NumEnemyT". Cambia el texto a "# of Enemies" y ajusta la fuente a algunos tamaños más pequeña que la del Title. Asegúrate de también poner el anchor en top/center y ajusta el Pos Y hasta que quede bien.

Ahora, ¡creemos una forma para que el jugador elija cuántos enemigos quiere! Hay muchas maneras de hacerlo, pero en este tutorial usaremos un slider.
Para crear un slider, haz clic derecho bajo Menu y selecciona "UI" → "Slider" y renómbralo a "EnemySlider". Pon el anchor en top/center también y ajusta el Pos Y para que quede justo debajo del texto "# of Enemies". En el inspector del slider, bajo Slider, cambia "Min Value" a "1" y "Max Value" a "3". También marca la casilla "Whole Number", ¡no podemos tener 1.5 enemigos en el campo!

Ahora que tenemos un slider, necesitamos una guía visual para que los jugadores sepan cuántos enemigos pueden seleccionar.
Crea 2 cuadros de texto más bajo Menu y nómbralos "1T" y "3T" respectivamente. Cambia el texto de "1T" a "1" y pon el anchor en middle/left. Ajusta Pos X y Pos Y bajo Rect Transform para que se alinee con el lado izquierdo del slider.
Repite el proceso con "3T" pero cambia el texto a "3", ancla a middle/right y alinéalo con el lado derecho del slider.

Ahora, creemos un botón de inicio. Bajo Menu en la ventana de jerarquía, crea "UI" → "Button" y renómbralo a "StartButton". Pon el anchor en bottom/center y ajusta el Pos Y para colocarlo donde prefieras. Si miras en la jerarquía, verás una flecha pegada al StartButton. Haz clic en ella para revelar un objeto Text. Cambia el texto de ese objeto Text a "Start".

<img src="../img/11_buttonUI.png" alt="Overview of Menu hierarchy" width="200"/>

¡Ahora tenemos la pantalla del menú lista! Tu pantalla del menú debería verse algo así:

<img src="../img/11_result.png" alt="Example Menu screen" width="800"/>

¡Pero espera! ¡Aún no hemos terminado! Si ejecutáramos el juego y presionáramos el botón Start, no pasaría nada. Queremos que la pantalla del menú desaparezca.
Para hacer esto, creemos otro script en nuestra carpeta Scripts dentro de la ventana Project, bajo Assets, y nómbralo "StartButton". Ábrelo y copia y pega el código que aparece abajo.

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class StartButton : MonoBehaviour
{

   public GameObject pop_up_box;


   public void popDown()
   {
       pop_up_box.SetActive(false);
   }

}
```

Este código hace que el GameObject que esté asignado a pop_up_box desaparezca cuando se llame a la función popDown(). Guarda, luego arrastra y suelta este script desde la carpeta Scripts al inspector del StartButton. Después arrastra el Menu desde la jerarquía hasta el campo vacío "Pop_up_box" bajo "Start Button (Script)".
Finalmente, bajo "Button" en el inspector del StartButton, haz clic en el signo "+" en el cuadro "On Click()". Arrastra el "StartButton" desde la jerarquía al recuadro que dice "None (Object)".
Luego despliega la barra "No Function", pasa el cursor sobre "StartButton", localiza la función popDown() y selecciónala.

<img src="../img/11_popDown.png" alt="Selecting popDown() function to activate when StartButton is clicked" width="600"/>

Ahora, si ejecutamos el juego y presionamos el botón Start, ¡la pantalla del menú desaparece!