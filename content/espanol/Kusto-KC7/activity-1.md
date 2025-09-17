---
title: "Activity 1: Login & Setup of the Cyber Environment"
draft: false
weight: 4
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/kMIKZhS5E4k" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## Primeros pasos

¡Muy bien, Ciberdefensores! Lo primero que deben hacer es configurar el entorno en el que buscarán a los atacantes. Para ello, abran los enlaces a continuación y sigan las instrucciones para, primero, configurar Azure Data Explorer (ADX) y, después, iniciar sesión en la sesión del Scoreboard.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/Resources.png?raw=true" alt= “Resources” width="60%" height="value">

### Configuración de Azure Data Explorer (ADX)

ADX es la herramienta principal que usan algunos defensores cibernéticos para la exploración y el análisis de datos. Lo bueno de ADX es que lo utilizan analistas de ciberseguridad en muchas de las organizaciones más pequeñas y más grandes del mundo.

Vamos a iniciar sesión y comenzar con ADX:

1.	Ve a [Azure Data Explorer](https://dataexplorer.azure.com/) e inicia sesión con tu cuenta de Microsoft.
    - Si no tienes una cuenta de Microsoft, créala ahora (son gratuitas).
2.	Haz clic en la pestaña Query en el lado izquierdo de la pantalla.

<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/ADX1.png?raw=true" alt= “ADX1” width="20%">

Los datos en ADX están organizados en una estructura jerárquica que consiste en **clusters, bases de datos y tablas**. Todos los registros de seguridad de Envolve Labs están almacenados en un único cluster. Necesitarás agregar este cluster a tu interfaz de ADX para poder empezar a ver los datos de los registros.

<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/ADX2.png?raw=true" alt= “ADX2” width="40%" height="value">

3.	Agrega un nuevo cluster usando el URI del cluster que te proporcione el instructor
    - Haz clic en add cluster
    - Ingresa el Connection URI: mstictraining.eastus

<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/ADX3.png?raw=true" alt= “ADX3” width="40%" height="value">

4.	Selecciona tu base de datos     
    - Expande la flecha desplegable junto a tu cluster. Deberías ver una base de datos llamada **SecurityLogs** dentro de él.     
    - Expande la flecha desplegable junto a la base de datos **SecurityLogs**.     
    - Haz clic en la base de datos **SecurityLogs**. Cuando la veas destacada, significa que la has seleccionado y ya puedes hacer consultas sobre las tablas que contiene.      

<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/ADX4_updated.png?raw=true" alt= “ADX4_updated” width="30%" height="value">

El gran espacio en blanco a la derecha de la lista de clusters es el área de consultas. Ahí usarás código KQL para escribir lo que llamamos queries, que se usan para interactuar con nuestros datos de registro.

<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/ADX5.png?raw=true" alt= “ADX5” width="60%" height="value">

### Configuración del Scoreboard

1.  Después de ir al [sitio del Scoreboard](https://aka.ms/kc7scoreboard), crea una cuenta de usuario. Asegúrate de usar un nombre de usuario y una contraseña que recuerdes, ya que te pedirá iniciar sesión de inmediato.
2.  Haz clic en el botón verde **"Join a new game"**
3.  Una vez dentro, ingresa la contraseña de la sesión: **GAMEON**

Deberías ver ahora el Scoreboard; cuando vayas a la pestaña de desafíos (challenges), deberías ver una lista como en la imagen de abajo. La necesitaremos más adelante en el entrenamiento, así que puedes minimizar el Scoreboard pero déjalo listo para usar.
<img src="https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/Scoreboard.png?raw=true" alt= “ADX3” width="value" height="value">

{{< alert theme="info" >}} ¡Listo! Ahora que estás configurado, es hora de poner manos a los datos. {{< /alert >}}