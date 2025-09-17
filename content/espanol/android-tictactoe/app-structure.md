---
title: "Game Application Structure"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 3
---

## Volviendo a los fundamentos
Ahora que el juego tiene el título correcto, profundicemos en todos estos archivos de la carpeta del juego. ¿Qué significan? ¿Cómo contribuye cada uno al juego?
<img src="../resources/_gen/images/app_structure_files.png" height="25%" width="25%" title="Expanded view of application files" alt="App files shown in Android Studio"/>

### AndroidManifest.xml
Todo proyecto en Android incluye un archivo de manifiesto. Para tu juego, este es el archivo `AndroidManifest.xml`. El archivo de manifiesto define los metadatos de tu juego; por ejemplo, puede definir el icono y el tema general de tu aplicación de juego.

### activity_main.xml
Este archivo está ubicado en la carpeta "layout". Como indica el nombre de la carpeta, los archivos en esta carpeta definen cómo se ve tu aplicación. Si miras el código de `activity_main.xml`, verás palabras clave como `TableLayout` o `TableRow`. La combinación de palabras clave en el archivo `activity_main.xml` crea el diseño para los botones selectores de juego (Player vs Player o Player vs Computer), el tablero de tic-tac-toe y el botón de reinicio. La palabra clave `TableLayout` indica que el diseño estará alineado al estilo de una tabla, que incluye columnas y filas. La palabra clave `TableRow` crea una nueva fila en el diseño, donde cada elemento adicional corresponde a una casilla en esa fila:
<img src="../resources/_gen/images/activity_main.png" height="30%" width="30%" title="Game board layout in rows" alt="Tic-Tac-Toe board with 5 rows. The first row includes the two game chooser buttons, followed by 3 rows by 3 columns for the Tic-Tac-Toe grid, and finally the fifth row with the restart button"/>

### MainActivity.kt
Este archivo está ubicado en la carpeta "java". El archivo contiene el código y la lógica de tu aplicación.

### colors.xml, strings.xml, styles.xml
Estos archivos se encuentran en la carpeta "values". Los archivos contienen valores que pueden ser referenciados por otros archivos XML y por el código de la aplicación.

## Poniéndolo todo junto
Todos estos archivos trabajan juntos para crear tu juego. El archivo `activity_main.xml` decide lo que se muestra. Cuando haces clic en los botones, se envían eventos desde `activity_main.xml` a `MainActivity.kt` para determinar qué ocurre al pulsar ese botón. Para valores reutilizables, `activity_main.xml` y `MainActivity.kt` pueden recurrir a `colors.xml`, `strings.xml` o `styles.xml` para usar esos valores desde un único lugar conveniente.