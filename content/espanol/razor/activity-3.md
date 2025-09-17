---
title: "Activity 3 - Create a Web App"
date: 2023-09-12T11:45:38-07:00
draft: false
weight: 7
---

## Instrucciones

### Crear un proyecto

1. Asegúrate de tener Visual Studio Code abierto.

2. En la **Activity bar**, selecciona **Explorer**.

3. Selecciona el botón **Create .NET Project**.

    El command palette desplegará una lista de tipos de proyecto para seleccionar.

4. De la lista, selecciona **Blazor Server App**.

5. Selecciona la carpeta en la que quieres que se guarde tu nueva app.

6. asígnale un nombre.

    La app se creará y aparecerá un menú **Solution** en el Explorer.

    <img src="../media/solution-explorer.png" alt="Screenshot of Solution Explorer in VS Code" />

¡Ahora tienes un sitio web!

### Revisar la estructura del proyecto Razor Pages

La siguiente tabla describe la estructura del proyecto que se generó.

|Name   | Description |
|-------|------------|
|Pages/	|Contains Razor Pages and supporting files. Each Razor page has a .cshtml file and a .cshtml.cs PageModel class file.|
|wwwroot/	|Contains static asset files like HTML, JavaScript, and CSS. |
|ContosoPizza.csproj	|Contains project configuration metadata, such as dependencies.|
|Program.cs|	Serves as the app's entry point and configures app behavior, like routing.|

Otras observaciones destacables:

* Archivos de Razor page y su archivo PageModel emparejado

    Los Razor pages se almacenan en el directorio Pages. Como se indicó arriba, cada Razor page tiene un archivo .cshtml y un archivo .cshtml.cs que contiene la clase PageModel. La clase PageModel permite separar la lógica y la presentación de una Razor page, define handlers de página para las solicitudes y encapsula propiedades y lógica de datos con ámbito en esa Razor page.

* La estructura del directorio Pages y el enrutamiento de solicitudes

    Razor Pages usa la estructura del directorio Pages como convención para enrutar las solicitudes. La siguiente tabla muestra cómo las URLs se mapean a nombres de archivo:

|URL|	Maps to Razor page|
|---|---------|
|www.domain.com	|Pages/Index.cshtml|
|www.domain.com/Index	|Pages/Index.cshtml|
|www.domain.com/Privacy	|Pages/Privacy.cshtml|
|www.domain.com/Error	|Pages/Error.cshtml|

Las subcarpetas en el directorio Pages se usan para organizar Razor pages. Por ejemplo, si existiera un directorio Pages/Products, las URLs reflejarían esa estructura:

|URL	|Maps to Razor page|
|-----|--------|
|www.domain.com/Products	|Pages/Products/Index.cshtml|
|www.domain.com/Products/Index	|Pages/Products/Index.cshtml|
|www.domain.com/Products/Create	|Pages/Products/Create.cshtml|

* Layout y otros archivos compartidos

Hay varios archivos que se comparten entre múltiples páginas. Estos archivos determinan elementos comunes de diseño e importaciones de página. La siguiente tabla describe el propósito de cada archivo.

|File	|Description|
|-------|----------|
|_ViewImports.cshtml	|Imports namespaces and classes that are used across multiple pages.|
|_ViewStart.cshtml	|Specifies the default layout for all Razor pages.|
|Pages/Shared/_Layout.cshtml	|This is the layout specified by the _ViewStart.cshtml file. Implements common layout elements across multiple pages.|
|Pages/Shared/_ValidationScriptsPartial.cshtml	|Provides validation functionality to all pages.|

### Ejecuta tu proyecto

1. Asegúrate de tener Visual Studio Code abierto y que en la **Activity bar** esté seleccionado **Explorer**.

2. En el **Solution Explorer**, haz clic derecho sobre el nombre de tu proyecto, selecciona **Debug** y luego **Start new instance**.

    Esto compilará y lanzará tu nuevo sitio web.

    <img src="../media/website1.png" alt="Screenshot of the website you just created" />

3. Haz clic en los enlaces ***Counter*** y ***Fetch Data*** para navegar por tu sitio web.

### Personalizar la página de inicio

Hagamos algunos cambios en la página de inicio para que sea más relevante para tu app.

1. En *Pages/Index.razor*, agrega un bloque de código C# con el siguiente código:


```C#
@code {
TimeSpan timeInBusiness = DateTime.Now - new DateTime(2010, 01, 17);
}
```

El código anterior:

* Calcula el tiempo que ha pasado desde que el negocio abrió.

2. Cambia el elemento ```PageTitle``` para que diga "Welcome to my first web page"

3. Cambia el ```h1``` para que diga "Welcome to my first Razor web app"

4. Reemplaza el texto restante con el siguiente código:

```CSHTML
<p class="lead">The best website in town for @Convert.ToInt32(timeInBusiness.TotalDays) days!</p>
```

El código anterior:

* Muestra el número de días que han pasado desde el 17 de enero de 2010.
    * El carácter @ se usa para cambiar de HTML a Razor Syntax.
    * El método Convert.ToInt32 se usa para convertir la propiedad TotalDays de la variable timeInBusiness a un entero.
    * La clase Convert forma parte del namespace System, que se importa automáticamente mediante el elemento ```<ImplicitUsings>``` en el archivo .csproj.

3. Guarda el archivo. Actualiza la pestaña del navegador con la app para mostrar los cambios. 

<img src="../media/end-of-activity-3.png" alt="Screenshot of site after changes from Activity 3" />; manteniéndolo claro para principiantes.