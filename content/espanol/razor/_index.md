---
title: "C#: Crea un Sitio Web con Razor"
description: "Guía introductoria sobre cómo crear un sitio web sencillo usando C#/Razor"
date: 2023-09-11T11:45:38-07:00
prereq: "Conceptos básicos de web, C#"
difficulty: "Intermedio"
draft: false
icon: "fas fa-code"
---

## Bienvenido

El objetivo de la actividad de hoy es aprender habilidades web y C# e incorporar lo que aprendas para crear un sitio web.

## Configuración inicial

El objetivo de la actividad de hoy es aprender habilidades web y C# e incorporar lo que aprendas para crear un sitio web. Vamos a preparar tu entorno.

Antes de comenzar con el desarrollo de aplicaciones en C#, el primer paso es seleccionar un entorno de programación. Para este taller hemos elegido Visual Studio Code, uno de los IDE más populares entre los desarrolladores de C#.

### Descargar Visual Studio Code
1. Abre una nueva ventana del navegador y navega a: <a href="https://code.visualstudio.com" target="_blank">https://code.visualstudio.com</a>.

2. En la ventana del navegador, selecciona el botón Download.

{{% panel theme="info" header="Note"%}}
La página de descarga de Visual Studio Code detecta automáticamente tu sistema operativo. Muestra la versión que se debe descargar para tu sistema operativo, como Linux, macOS o Windows.
{{% /panel %}}

3. Espera a que termine de descargarse el archivo del instalador.

El nombre del archivo del instalador será parecido al siguiente (para un PC con Windows): VSCodeUserSetup-x64-1.81.0.exe.

{{% panel theme="info" header="Note"%}}
El nombre del archivo depende de la versión actual de Visual Studio Code y del sistema operativo de tu equipo.
{{% /panel %}}

4. Cierra la ventana del navegador.

### Instalar Visual Studio Code
1. En tu PC, abre una aplicación de explorador de archivos y navega a la carpeta de descargas de tu equipo.

2. En el explorador de archivos, selecciona y ejecuta el archivo del instalador de Visual Studio Code.

    En un PC con Windows, puedes hacer doble clic en el archivo del instalador para iniciar el proceso de instalación. Por ejemplo, haz doble clic en VSCodeUserSetup-x64-1.81.0

{{% panel theme="info" header="Note"%}}
Puedes instalar Visual Studio Code usando el instalador de usuario (User Installer) o el instalador para el sistema (System Installer). El instalador de usuario instala Visual Studio Code solo para el usuario actual, mientras que el instalador para el sistema lo instala para todos los usuarios. El instalador de usuario es la opción recomendada para la mayoría de los usuarios.
{{% /panel %}}

Después de un momento, aparecerá la ventana de diálogo **Setup - Microsoft Visual Studio Code**.

<img src="media/vscodeInstaller.png" alt="Screenshot showing the Visual Studio Code Installer" />

3. Selecciona I accept the license agreement y continúa siguiendo las instrucciones en pantalla para completar la instalación.

    Acepta las opciones predeterminadas durante el resto de la instalación.

    Para instrucciones detalladas de instalación, consulta la siguiente página de documentación de Visual Studio Code: <a href="https://code.visualstudio.com/docs/setup/windows" target="_blank">https://code.visualstudio.com/docs/setup/windows</a>.

### Instalar el SDK de .NET

{{% panel theme="info" header="How to check if you have .NET installed"%}}
Puedes comprobar si ya tienes .NET instalado abriendo una ventana de Terminal y escribiendo <code>dotnet --version</code> y presionando la tecla Enter.
{{% /panel %}}

1. Abre una nueva ventana del navegador.

2. Para abrir la página de descarga del SDK de .NET, navega a la siguiente URL:

    <a href="https://dotnet.microsoft.com/download" target="_blank">https://dotnet.microsoft.com/download</a>

3. En la página Download .NET, selecciona la versión recomendada del SDK de .NET.

4. Espera a que termine de descargarse el archivo del instalador.

5. Ejecuta el archivo del instalador del SDK de .NET.

    En un PC con Windows, puedes encontrar la carpeta Descargas usando el Explorador de archivos. Haz doble clic en el archivo de instalación para comenzar el proceso.

6. En la ventana del instalador del SDK de .NET, selecciona Install.

7. Espera a que finalice la instalación.

    La instalación debería tardar alrededor de un minuto. Una vez completada, aparecerá un mensaje confirmando que la instalación se realizó correctamente.

8. Para cerrar la ventana del instalador, selecciona Close.

## Tabla de contenidos

<details close>
<summary>Tabla de contenidos</summary>
{{% children /%}}
</details>