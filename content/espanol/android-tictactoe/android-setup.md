---
title: "Android Setup"
date: 2021-03-13T14:17:07.42-07:00
draft: false
weight: 2
---
Sigue los pasos a continuación para instalar Android Studio en tu ordenador. Si ya tienes Android Studio instalado, ábrelo y salta al siguiente paso.

Estos pasos tienen ejemplos para instalar en computadoras con Windows. Sin embargo, los pasos son similares para otros tipos de equipos también.

## Descargar e instalar Android Studio
1. [Descarga Android Studio](https://developer.android.com/studio/) para tu sistema operativo.
2. [Sigue estos pasos](https://developer.android.com/studio/install) para instalar Android Studio.

## Configurar la variable de entorno JAVA_HOME
Android Studio incluye una versión de Java necesaria para que ciertas partes de la aplicación funcionen. Sigue los pasos a continuación para configurar la variable de entorno `JAVA_HOME` en tu equipo, la cual indica a estas herramientas dónde encontrar Java:
1. En el cuadro de búsqueda en la esquina inferior izquierda de la pantalla, escribe `env`.
2. Selecciona el programa "Best Match" `Edit the system environment variables`.
<img src="../resources/_gen/images/edit_env_variable.png" height="30%" width="30%" title="Edit system environment variables" alt="Edit system environment variables"/>
3. Haz clic en `Environment Variables...`.
4. Haz clic en `New...` en la sección 'User variables'.
5. Escribe JAVA_HOME como nombre de la variable.
6. Copia lo siguiente en el valor de la variable:
```
C:\Program Files\Android\Android Studio\jre
```
7. Haz clic en OK.
<img src="../resources/_gen/images/set_java_home.gif" height="40%" width="40%" title="Setting JAVA_HOME" alt="shows steps to set the JAVA_HOME environment variable"/>

{{% notice tip %}}
Te recomendamos encarecidamente que reinicies tu ordenador ahora para que Android Studio se abra correctamente.
{{% /notice %}}

## Iniciar Android Studio
Una vez instalado, abre Android Studio para trabajar en la app.

{{% notice tip %}}
Hay varias maneras de iniciar la aplicación Android Studio en tu equipo con Windows. Aquí hay dos métodos:
#### Método 1
1. Haz clic en el icono de Windows en la esquina inferior izquierda de tu ordenador.
2. Desplázate por la lista hasta que veas la carpeta `Android Studio`.
3. Haz clic en la carpeta `Android Studio` para expandirla.
4. Haz clic en la aplicación `Android Studio` dentro de la carpeta para iniciarla.

#### Método 2
1. En el cuadro de búsqueda en la esquina inferior izquierda de la pantalla, escribe `Android Studio`.
2. En la ventana de resultados, si "Best Match" resalta `Android Studio`, haz clic en la aplicación `Android Studio` o presiona `ENTER` en tu teclado.
{{% /notice %}}

## Abrir archivos del proyecto
1. Haz clic en `Open an Existing Project` en la pantalla de inicio de Android Studio.
2. Busca la ubicación donde descargaste los archivos del proyecto.
3. Selecciona la carpeta 'TicTacToe' dentro de la carpeta 'TicTacToe' que descomprimiste anteriormente.
   - La carpeta 'TicTacToe' que debes seleccionar debería tener un icono verde de Android junto a ella, indicando que es una carpeta de proyecto Android.
<img src="../resources/_gen/images/open_android_project.gif" height="40%" width="40%" title="Open TicTacToe project" alt="Shows how to open the TicTacToe project in Android Studio"/>

Ejecuta Android Studio y abre el proyecto. Tu vista se verá similar a esto:
<img src="../resources/_gen/images/android_studio.png" height="60%" width="60%" title="Android Studio IDE" alt="Example of Android Studio IDE"/>

## Aceptar licencias
Antes de poder ejecutar el código, necesitarás aceptar las licencias de Android siguiendo los pasos a continuación:
1. Haz clic en el botón `Terminal` en la parte inferior de la ventana de Android Studio.
2. Escribe el siguiente comando, reemplazando '<USER_NAME>' por el nombre de usuario de tu ordenador.
```
C:\Users\<USER_NAME>\AppData\Local\Android\Sdk\tools\bin\sdkmanager --licenses
```
3. Escribe `y` y presiona `ENTER` en los avisos para aceptar las licencias. Esto será necesario varias veces.
<img src="../resources/_gen/images/accept_licenses.gif" height="60%" width="60%" title="Accepting Android licenses" alt="shows the steps needed to accept Android licenses"/>