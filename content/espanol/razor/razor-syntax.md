---
title: "Razor Basics"
date: 2023-09-12T11:45:38-07:00
draft: false
weight: 5
---

## Sintaxis de Razor

### Reglas principales de sintaxis de Razor
Razor soporta C# y usa el símbolo @ para hacer la transición de HTML a C#. Razor evalúa expresiones de C# y las renderiza en la salida HTML.

Cuando un símbolo @ va seguido de una palabra reservada de Razor, pasa a un marcado específico de Razor. De lo contrario, pasa a HTML normal.

Para escapar un símbolo @ en el marcado Razor, usa un segundo @:

```csharp
<p>@@Username</p>
```

El código anterior se renderiza en HTML con un solo símbolo @.

Hay algunas reglas básicas que recordar al escribir código Razor.

* Los bloques de código Razor están encerrados en ```@{ ... }```
* Las expresiones en línea (variables y funciones) empiezan con ```@```
* Las sentencias de código terminan con punto y coma (```;```)
* Las cadenas de texto van entre comillas
* El código C# distingue entre mayúsculas y minúsculas
* Los archivos C# tienen la extensión .cshtml o .razor

#### Expresiones implícitas de Razor
Las expresiones implícitas de Razor comienzan con ```@``` seguido de código C#.

```csharp
<p>@DateTime.Now</p>
<p>@DateTime.IsLeapYear(2016)</p>
```

Con la excepción de la palabra clave C# ```await```, las expresiones implícitas no deben contener espacios.

Las expresiones implícitas ***no pueden*** contener genéricos de C#, ya que los caracteres dentro de (```<>```) se interpretan como una etiqueta HTML. 

#### Expresiones explícitas de Razor
Las expresiones explícitas de Razor consisten en un símbolo @ con paréntesis balanceados. Para renderizar la hora de la semana pasada, se usa el siguiente marcado Razor:

```csharp
<p>Last week this time: @(DateTime.Now - TimeSpan.FromDays(7))</p>
```
Cualquier contenido dentro de los paréntesis @() se evalúa y se renderiza en la salida.

Las expresiones explícitas pueden usarse para concatenar texto con el resultado de una expresión:

```csharp
@{
    var joe = new Person("Joe", 33);
}

<p>Age@(joe.Age)</p>
```

Sin la expresión explícita, ```<p>Age@joe.Age</p>``` se interpreta como una dirección de correo electrónico y se renderiza literalmente como ```<p>Age@joe.Age</p>```. Cuando se escribe como expresión explícita, se renderiza ```<p>Age33</p>```.

#### Bloques de código Razor
Los bloques de código Razor comienzan con @ y están encerrados por {}. A diferencia de las expresiones, el código C# dentro de los bloques no se renderiza. Los bloques de código y las expresiones en una vista comparten el mismo alcance y se definen en orden:

Dentro de los bloques de código, declara funciones locales con marcado para que sirvan como métodos de plantilla:

```csharp
@{
    void RenderName(string name)
    {
        <p>Name: <strong>@name</strong></p>
    }

    RenderName("Mahatma Gandhi");
    RenderName("Martin Luther King, Jr.");
}
```
El código renderiza el siguiente HTML:

```html
<p>Name: <strong>Mahatma Gandhi</strong></p>
<p>Name: <strong>Martin Luther King, Jr.</strong></p>
```

#### Renderizado condicional de atributos
Razor omite automáticamente los atributos que no son necesarios. Si el valor pasado es null o false, el atributo no se renderiza.

Por ejemplo, considera el siguiente Razor:

```csharp
<div class="@false">False</div>
<div class="@null">Null</div>
<div class="@("")">Empty</div>
<div class="@("false")">False String</div>
<div class="@("active")">String</div>
<input type="checkbox" checked="@true" name="true" />
<input type="checkbox" checked="@false" name="false" />
<input type="checkbox" checked="@null" name="null" />
```

El marcado Razor anterior genera el siguiente HTML:

```html
<div>False</div>
<div>Null</div>
<div class="">Empty</div>
<div class="false">False String</div>
<div class="active">String</div>
<input type="checkbox" checked="checked" name="true">
<input type="checkbox" name="false">
<input type="checkbox" name="null">
```

### Trabajar con objetos
La programación en el servidor a menudo implica objetos.

El objeto "DateTime" es un objeto integrado típico en ASP.NET, pero los objetos también pueden ser definidos por uno mismo para describir una página web, un cuadro de texto, un archivo, un registro de base de datos, etc.

Los objetos pueden tener métodos que pueden ejecutar. Un registro de base de datos podría tener un método "Save", un objeto imagen podría tener un método "Rotate", un objeto correo podría tener un método "Send", y así sucesivamente.

Los objetos también tienen propiedades que describen sus características. Un registro de base de datos podría tener propiedades FirstName y LastName (entre otras).

El objeto DateTime de ASP.NET tiene una propiedad Now (escrita como DateTime.Now), y la propiedad Now tiene una propiedad Day (escrita como DateTime.Now.Day). El ejemplo a continuación muestra cómo acceder a algunas propiedades del objeto DateTime:

```html
<table border="1">
<tr>
<th width="100px">Name</th>
<td width="100px">Value</td>
</tr>
<tr>
<td>Day</td><td>@DateTime.Now.Day</td>
</tr>
<tr>
<td>Hour</td><td>@DateTime.Now.Hour</td>
</tr>
<tr>
<td>Minute</td><td>@DateTime.Now.Minute</td>
</tr>
<tr>
<td>Second</td><td>@DateTime.Now.Second</td>
</tr>
</td>
</table>
```

### Estructuras de control
Las estructuras de control son una extensión de los bloques de código. Todos los aspectos de los bloques de código (transición a marcado, C# en línea) también se aplican a las siguientes estructuras:

#### Condicionales ```@if, else if, else, y @switch```
```@if``` controla cuándo se ejecuta el código:

```csharp
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

```else``` y ```else if``` no requieren el símbolo @:

```csharp
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
else if (value >= 9876)
{
    <p>The value is large.</p>
}
else
{
    <p>The value is odd and small.</p>
}
```

El siguiente marcado muestra cómo usar una sentencia switch:

```csharp
@switch (value)
{
    case 1:
        <p>The value is 1!</p>
        break;
    case 9876:
        <p>Your number is 9876!</p>
        break;
    default:
        <p>Your number wasn't 1 or 9876.</p>
        break;
}
```

#### Bucles ```@for, @foreach, @while, y @do while```

Se puede renderizar HTML con plantillas usando sentencias de control de bucle. Para renderizar una lista de personas:

```csharp
@{
    var people = new Person[]
    {
          new Person("Jade", 31),
          new Person("Maxwell", 29),
          ...
    };
}
```

Se admiten las siguientes sentencias de bucle:

```@for```

```csharp
@for (var i = 0; i < people.Length; i++)
{
    var person = people[i];
    <p>Name: @person.Name</p>
    <p>Age: @person.Age</p>
}
```

```@foreach```

```csharp
@foreach (var person in people)
{
    <p>Name: @person.Name</p>
    <p>Age: @person.Age</p>
}
```

```@while```

```csharp
@{ var i = 0; }
@while (i < people.Length)
{
    var person = people[i];
    <p>Name: @person.Name</p>
    <p>Age: @person.Age</p>

    i++;
}
```

```@do while```

```csharp
@{ var i = 0; }
@do
{
    var person = people[i];
    <p>Name: @person.Name</p>
    <p>Age: @person.Age</p>

    i++;
} while (i < people.Length);
```
