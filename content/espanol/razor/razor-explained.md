---
title: "Razor Basics"
date: 2023-09-12T11:45:38-07:00
draft: false
weight: 4
---

## Entender cuándo y por qué usar Razor

### Los beneficios de Razor Pages
Razor es una sintaxis de marcado que te permite incrustar código del lado del servidor (C#) dentro de páginas web.

El código del lado del servidor puede crear contenido web dinámico sobre la marcha, mientras que una página web se escribe al navegador. Cuando se solicita una página web, el servidor ejecuta el código del lado del servidor dentro de la página antes de devolverla al navegador. Al ejecutarse en el servidor, el código puede realizar tareas complejas, como acceder a bases de datos.

Razor está basado en ASP.NET y está diseñado para crear aplicaciones web. Tiene la potencia del marcado tradicional de ASP.NET, pero es más fácil de usar y de aprender.

Los beneficios incluyen:

* Configuración sencilla para aplicaciones web dinámicas usando HTML, CSS y C#.
* Archivos organizados por característica para facilitar el mantenimiento.
* Combina el marcado con código C# del lado del servidor usando la sintaxis Razor.

Razor Pages utiliza Razor para incrustar código del lado del servidor en páginas web. La sintaxis Razor combina HTML y C# para definir la lógica de renderizado dinámico. Esto significa que puedes usar variables y métodos de C# dentro de tu marcado HTML para generar contenido web dinámico en el servidor en tiempo de ejecución. Es importante entender que Razor Pages no son un reemplazo de HTML, CSS o JavaScript. Son una forma de combinar estas tecnologías para crear contenido web dinámico.

### Cuándo usar Razor Pages
Usa Razor Pages en tu aplicación ASP.NET Core cuando:

* Quieras generar una interfaz web dinámica.
* Prefieras un enfoque centrado en páginas.
* Quieras reducir la duplicación con partial views.

Razor Pages simplifica la organización de páginas en ASP.NET Core al mantener las páginas relacionadas y su lógica juntas en su propio namespace y directorio, lo que facilita su comprensión para principiantes.