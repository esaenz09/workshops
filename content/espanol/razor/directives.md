---
title: "Razor Directives"
date: 2023-09-13T11:45:38-07:00
draft: false
weight: 6
---

## Directivas
Las directivas de Razor se representan mediante expresiones implícitas con palabras clave reservadas que siguen al símbolo @. Una directiva típicamente cambia la forma en que se analiza una vista o habilita funcionalidades diferentes.

Entender cómo Razor genera código para una vista facilita comprender cómo funcionan las directivas.

```csharp
@{
    string quote = "Getting old ain't for wimps! - Anonymous";
}

<div>Quote of the Day: @quote</div>
```

El código genera una clase similar a la siguiente:

```csharp
public class _Views_Something_cshtml : RazorPage<dynamic>
{
    public override async Task ExecuteAsync()
    {
        string output = "Getting old ain't for wimps! - Anonymous";

        WriteLiteral("/r/n<div>Quote of the Day: ");
        Write(output);
        WriteLiteral("</div>");
    }
}
```

### ```@attribute```
La directiva ```@attribute``` agrega el atributo proporcionado a la clase de la página o vista generada. El siguiente ejemplo añade el atributo [Authorize]:

```csharp
@attribute [Authorize]
```

La directiva ```@attribute``` también puede usarse para suministrar una plantilla de ruta basada en una constante en un componente Razor. En el siguiente ejemplo, la directiva ```@page``` en un componente se reemplaza por la directiva ```@attribute``` y la plantilla de ruta basada en la constante Constants.CounterRoute, que se establece en otra parte de la aplicación como "/counter":

```csharp
@page "/counter"
@attribute [Route(Constants.CounterRoute)]
```

### ```@code```
Este escenario solo se aplica a componentes Razor (.razor).

El bloque ```@code``` permite que un componente Razor agregue miembros C# (campos, propiedades y métodos) a un componente:

```csharp
@code {
    // C# members (fields, properties, and methods)
}
```

Para componentes Razor, ```@code``` es un alias de ```@functions``` y se recomienda sobre ```@functions```. Se permiten más de un bloque ```@code```.

### ```@functions```
La directiva ```@functions``` permite agregar miembros C# (campos, propiedades y métodos) a la clase generada:

```csharp
@functions {
    // C# members (fields, properties, and methods)
}
```

En componentes Razor, use ```@code``` en lugar de ```@functions``` para agregar miembros C#.

Por ejemplo:

```csharp
@functions {
    public string GetHello()
    {
        return "Hello";
    }
}

<div>From method: @GetHello()</div> 
```

El código genera el siguiente marcado HTML:

```html
<div>From method: Hello</div>
```

El siguiente código es la clase C# Razor generada:

```csharp
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc.Razor;

public class _Views_Home_Test_cshtml : RazorPage<dynamic>
{
    // Functions placed between here 
    public string GetHello()
    {
        return "Hello";
    }
    // And here.
#pragma warning disable 1998
    public override async Task ExecuteAsync()
    {
        WriteLiteral("\r\n<div>From method: ");
        Write(GetHello());
        WriteLiteral("</div>\r\n");
    }
#pragma warning restore 1998
```

Los métodos de ```@functions``` sirven como métodos de plantillas cuando contienen marcado:

```csharp
@{
    RenderName("Mahatma Gandhi");
    RenderName("Martin Luther King, Jr.");
}

@functions {
    private void RenderName(string name)
    {
        <p>Name: <strong>@name</strong></p>
    }
}
```

El código renderiza el siguiente HTML:

```html
<p>Name: <strong>Mahatma Gandhi</strong></p>
<p>Name: <strong>Martin Luther King, Jr.</strong></p>
```

### ```@implements```
La directiva ```@implements``` implementa una interfaz para la clase generada.

El siguiente ejemplo implementa System.```IDisposable``` para que se pueda llamar al método Dispose:

```csharp
@implements IDisposable

<h1>Example</h1>

@functions {
    private bool _isDisposed;

    ...

    public void Dispose() => _isDisposed = true;
}
```

### ```@inherits```

La directiva ```@inherits``` proporciona control total sobre la clase de la que hereda la vista:

```csharp
@inherits TypeNameOfClassToInheritFrom
```

El siguiente código es un tipo de página Razor personalizada:

```csharp
using Microsoft.AspNetCore.Mvc.Razor;

public abstract class CustomRazorPage<TModel> : RazorPage<TModel>
{
    public string CustomText { get; } = 
        "Gardyloo! - A Scottish warning yelled from a window before dumping" +
        "a slop bucket on the street below.";
}
```

El CustomText se muestra en una vista:

```chsarp
@inherits CustomRazorPage<TModel>

<div>Custom text: @CustomText</div>
```

El código renderiza el siguiente HTML:

```html
<div>
    Custom text: Bumbershoot - Another word for an umbrella.
</div>
```

```@model``` y ```@inherits``` pueden usarse en la misma vista. ```@inherits``` puede estar en un archivo _ViewImports.cshtml que la vista importe:

```csharp
@inherits CustomRazorPage<TModel>
```

El siguiente código es un ejemplo de una vista fuertemente tipada:

```csharp
@inherits CustomRazorPage<TModel>

<div>The Login Email: @Model.Email</div>
<div>Custom text: @CustomText</div>
```

Si se pasa "jade@nuevofoundation.org" en el modelo, la vista genera el siguiente marcado HTML:

```html
<div>The Login Email: jade@nuevofoundation.org</div>
<div>
    Custom text: Bumbershoot - Another word for an umbrella.
</div>
```

### ```@inject```

La directiva ```@inject``` permite a la Página Razor inyectar un servicio desde el contenedor de servicios en una vista. 

### ```@layout```

Este escenario solo se aplica a componentes Razor (.razor).

La directiva ```@layout``` especifica un diseño para componentes Razor enrutables que tienen una directiva ```@page```. Los componentes de diseño se usan para evitar duplicación de código e inconsistencias.

### ```@model```

Este escenario solo se aplica a vistas MVC y Razor Pages (.cshtml).

La directiva ```@model``` especifica el tipo del modelo pasado a una vista o página:

```csharp
@model TypeNameOfModel
```

En una aplicación ASP.NET Core MVC o Razor Pages creada con cuentas de usuario individuales, Views/Account/Login.cshtml contiene la siguiente declaración del modelo:

```csharp
@model LoginViewModel
```

La clase generada hereda de RazorPage<LoginViewModel>:

```csharp
public class _Views_Account_Login_cshtml : RazorPage<LoginViewModel>
```

Razor expone una propiedad Model para acceder al modelo pasado a la vista:

```html
<div>The Login Email: @Model.Email</div>
```

La directiva ```@model``` especifica el tipo de la propiedad Model. La directiva especifica la T en ```RazorPage<T>``` de la clase generada de la que deriva la vista. Si no se especifica la directiva ```@model```, la propiedad Model es de tipo dynamic. Para más información, consulte Modelos fuertemente tipados y la palabra clave ```@model```.

### ```@namespace```

La directiva ```@namespace```:

* Establece el espacio de nombres de la clase de la página Razor generada, vista MVC o componente Razor.
* Establece los espacios de nombres derivados raíz de las clases de páginas, vistas o componentes desde el archivo de importaciones más cercano en el árbol de directorios, _ViewImports.cshtml (vistas o páginas) o _Imports.razor (componentes Razor).

```csharp
@namespace Your.Namespace.Here
```

Para el ejemplo de Razor Pages mostrado en la siguiente tabla:

* Cada página importa Pages/_ViewImports.cshtml.
* Pages/_ViewImports.cshtml contiene @namespace Hello.World.
* Cada página tiene Hello.World como raíz de su espacio de nombres.

|Page|	Namespace|
|---|---|
|Pages/Index.cshtml|	Hello.World|
|Pages/MorePages/Page.cshtml	|Hello.World.MorePages|
|Pages/MorePages/EvenMorePages/Page.cshtml|	Hello.World.MorePages.EvenMorePages|

Las relaciones anteriores se aplican a archivos de importación usados con vistas MVC y componentes Razor.

Cuando múltiples archivos de importación tienen una directiva ```@namespace```, se utiliza el archivo más cercano a la página, vista o componente en el árbol de directorios para establecer el espacio de nombres raíz.

Si la carpeta EvenMorePages en el ejemplo anterior tiene un archivo de importaciones con ```@namespace``` Another.Planet (o el archivo Pages/MorePages/EvenMorePages/Page.cshtml contiene ```@namespace``` Another.Planet), el resultado se muestra en la siguiente tabla.

|Page|	Namespace|
|---|---|
|Pages/Index.cshtml|	Hello.World|
|Pages/MorePages/Page.cshtml|	Hello.World.MorePage|
|Pages/MorePages/EvenMorePages/Page.cshtml|	Another.Planet|

### ```@page```

La directiva ```@page``` tiene diferentes efectos dependiendo del tipo de archivo en el que aparezca. La directiva:

* En un archivo .cshtml indica que el archivo es una Razor Page. 
* Especifica que un componente Razor debe manejar solicitudes directamente. 

### ```@preservewhitespace```

Este escenario solo se aplica a componentes Razor (.razor).

Cuando se establece en false (por defecto), se elimina el espacio en blanco en el marcado renderizado de los componentes Razor (.razor) si:

* Está al principio o al final dentro de un elemento.
* Está al principio o al final dentro de un parámetro RenderFragment. Por ejemplo, contenido hijo pasado a otro componente.
* Precede o sigue a un bloque de código C#, como ```@if``` o ```@foreach```.

### ```@section```
Este escenario solo se aplica a vistas MVC y Razor Pages (.cshtml).

La directiva ```@section``` se usa junto con los diseños de MVC y Razor Pages para permitir que las vistas o páginas rendericen contenido en diferentes partes de la página HTML. 

### ```@typeparam```

Este escenario solo se aplica a componentes Razor (.razor).

La directiva ```@typeparam``` declara un parámetro de tipo genérico para la clase del componente generada:

```csharp
@typeparam TEntity
```

Se admiten tipos genéricos con restricciones where:

```csharp
@typeparam TEntity where TEntity : IEntity
```

### ```@using```

La directiva ```@using``` agrega la directiva using de C# a la vista generada:

```csharp
@using System.IO
@{
    var dir = Directory.GetCurrentDirectory();
}
<p>@dir</p>
```

En componentes Razor, ```@using``` también controla qué componentes están en el ámbito.

## Atributos de directiva
Los atributos de directiva de Razor se representan mediante expresiones implícitas con palabras clave reservadas que siguen al símbolo ```@```. Un atributo de directiva típicamente cambia la forma en que se analiza un elemento o habilita funcionalidades diferentes.

### ```@attributes```
Este escenario solo se aplica a componentes Razor (.razor).

```@attributes``` permite que un componente renderice atributos no declarados. 

### ```@bind```
Este escenario solo se aplica a componentes Razor (.razor).

El enlace de datos en componentes se logra con el atributo ```@bind```. 

```html
<input type="checkbox" @bind="todo.IsDone" />
```
Este ejemplo enlaza la propiedad ```IsDone``` del objeto ```todo``` con la casilla de verificación.

### ```@bind:culture```
Este escenario solo se aplica a componentes Razor (.razor).

Use el atributo ```@bind:culture``` con el atributo ```@bind``` para proporcionar un ```System.Globalization.CultureInfo``` para analizar y dar formato a un valor.

### ```@on{EVENT}```
Este escenario solo se aplica a componentes Razor (.razor).

Razor proporciona características de manejo de eventos para componentes.

```html
<button @onclick="AddTodo">Add todo</button>
```

Con este código, cuando alguien haga clic en el botón, se llamará al método ```AddToDo```.

### ```@ref```
Este escenario solo se aplica a componentes Razor (.razor).

Las referencias de componentes (```@ref```) proporcionan una forma de referenciar una instancia de componente para que pueda emitir comandos a esa instancia. 

## Palabras clave reservadas de Razor
### Palabras clave de Razor
* page
* namespace
* functions
* inherits
* model
* section

Las palabras clave de Razor se escapan con ```@(Razor Keyword)``` (por ejemplo, ```@(functions)```).

### Palabras clave de C# en Razor
* case
* do
* default
* for
* foreach
* if
* else
* lock
* switch
* try
* catch
* finally
* using
* while

Las palabras clave de C# en Razor deben escaparse doblemente con ```@(@C# Razor Keyword)``` (por ejemplo, ```@(@case)``` ). El primer ```@``` escapa al analizador de Razor. El segundo ```@``` escapa al analizador de C#.

### Palabras clave reservadas no usadas por Razor
* class; mantenerlo claro para principiantes.

        Preserve technical terms, code syntax, and formatting. Only translate comments that explain concepts.
        Adapt cultural references appropriately. Don't translate the header key title; don't translate the image html