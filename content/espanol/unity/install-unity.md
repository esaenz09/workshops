---
title: "Installing Unity"
date: 2021-10-06T11:45:38-07:00
draft: false
weight: 1
---

Necesitamos ayudar a Nuvi a derrotar a los alienígenas, pero programar todo desde cero puede ser demasiado por ahora.
Unity es una herramienta que simplifica varias partes básicas de la creación de juegos, así que todo lo que tenemos que hacer es arrastrar y soltar objetos y escribir un poco de código sencillo en C#.

{{< notice info >}}
#### ¿Por qué usar Unity cuando hay otras herramientas disponibles?

Unity tiene varios aspectos excelentes, especialmente si estás empezando en el desarrollo de juegos. Es multiplataforma, lo que significa que puedes desarrollar un juego para, por ejemplo, ordenadores y teléfonos móviles. Es amigable para quienes aprenden a programar. ¡Y lo mejor es que cuenta con una comunidad grande y de apoyo!

Algunos juegos desarrollados en Unity incluyen: *Subway Surfers*, *Hearthstone*, *Cytus*, *Pokemon Go*, *Overcooked*, *Cuphead*, *Hollow Knight*, *Among Us* y *Genshin Impact*.
Solo con esta lista puedes notar que hay tanto títulos independientes como AAA, y juegos para una variedad de plataformas. Tanto si quieres trabajar en una gran empresa como si quieres desarrollar por tu cuenta, ¡es buena idea tener experiencia con Unity!
{{< /notice >}}

Así que, antes de que podamos hacer cualquier cosa, ¡necesitas descargar e instalar Unity!
Incluso si ya tienes Unity instalado, revisa esta actividad para asegurarte de que tienes la configuración correcta.

## Paso 1: Descargar Unity

Primero, vamos a [elegir y descargar Unity](https://unity3d.com/get-unity/download?_ga=2.142217974.513534012.1631151100-1023620192.1630193772).

1. Haz clic en "Choose your Unity + download".

2. Haz clic en "Student and hobbyist" y bajo "Personal" o "Student" si tienes un correo electrónico de estudiante, selecciona "Get Started". 

3. Desplázate hacia abajo en la página bajo "1. Download the Unity Hub" y descarga la versión correspondiente a tu equipo.  

{{< notice note >}}
Para este taller usamos la versión "2019.4.19f1" en los contenidos y las capturas de pantalla. Si quieres usar exactamente esta versión, en la misma página bajo "2. Choose your Unity version", selecciona "Visit the download archive" para encontrar la misma versión que usamos en el taller. Si no, puede haber pequeños cambios en la interfaz de usuario en versiones más recientes. Si decides adentrarte en el desarrollo de juegos con Unity, ¡no olvides revisar las versiones más recientes!
{{< /notice >}}

4. Después de que Unity termine de descargarse, abre Unity, lo que iniciará la configuración de Unity Hub, una aplicación que te ayudará a gestionar tus proyectos de Unity.

5. Aparecerá una ventana emergente. Acepta los acuerdos de usuario, activa la licencia, selecciona la carpeta de destino donde quieres descargar en tu ordenador, instala y luego ejecuta Unity Hub seleccionando "Finish".

## Paso 2: Unity Hub

1. Inicia sesión con tu Unity ID: aparecerá el instalador de Unity Hub. Una vez que pulses instalar, te llevarán a una página donde debes crear un Unity ID. Si aún no tienes uno, crea uno nuevo. Si ya tienes, selecciona "I already have a Unity ID" e introduce tus datos.

2. Tras introducir tu información, la página te pedirá que elijas una plantilla para un microgame. Esto solo ocurre porque elegimos "First-Time Users", así que Unity quiere que los usuarios nuevos prueben los proyectos dados para ayudarles a entender mejor Unity.

3. Usaremos nuestros propios proyectos para enseñar, así que por ahora puedes elegir una plantilla cualquiera que quieras explorar más tarde y pulsar "continue" y "Launch Unity". Unity lanzará el microgame, pero como no lo usaremos, simplemente cierra Unity.

4. Si tu versión de Unity no es 2019.4, abre Unity Hub y, a la izquierda de la ventana, selecciona "Installs". Haz clic en el botón "ADD" y selecciona la versión que quieras. Puedes seleccionar la versión más reciente o la que usamos para este proyecto, **"2019.4.19f1 (LTS)"**. Luego, Unity Hub te llevará a una página donde puedes elegir las librerías que quieres incluir. ¡Asegúrate de que estén seleccionados Windows y Mac Build Support!

## Paso 3: ¡Empecemos!
Para comenzar un proyecto nuevo, abre Unity Hub y haz clic en el botón azul que dice "NEW". Nombra tu proyecto como prefieras y elige una ubicación para crear la carpeta del proyecto. Asegúrate de tener seleccionado "2D" como plantilla del proyecto, como se muestra en la captura.

![Creating a new 2D Unity project](../img/0_new_project_edited.png)