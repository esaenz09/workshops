---
title: "Web Developer Guidelines"
date: 2019-07-22T14:08:32-07:00
draft: false
weight: 4
---

Este documento es para **desarrolladores de sitios web solamente** para cambiar las plantillas y el estilo del [Nuevo Foundation workshop project](https://github.com/nuevoFoundation/workshops).

## Antes de comenzar

Antes de agregar/actualizar el sitio web, asegúrese de haberse sincronizado con el equipo del proyecto y con el trabajo existente en el [Project Backlog](https://github.com/NuevoFoundation/workshops/projects/1).

## Configuración

Siga las instrucciones en la página [Getting Started](../getting-started/) para instalar Git y Hugo y probar el proyecto localmente.

## Estilos y estructura del diseño web

- **Images:** Las imágenes del sitio web deben estar en `themes/images`
- **CSS:** Ignore los archivos SCSS y use solo archivos CSS en `/themes/docdock/static/css/`. Asegúrese de agregar una referencia al CSS que quiera incluir en el archivo `head.html` en `/themes/docdock/layouts/partials/flex/head.html`

## Desglosando una página de taller

- **Full page template**: Para ver todos los componentes de una página, incluyendo encabezado, menú, cuerpo y pie, vea `/themes/docdock/layouts/_default/baseof.html`
- **Head**: Metadatos, CSS y JS en `/themes/docdock/layouts/partials/flex/head.html`
- **Top / Menu Navigation**: No use los valores de config.toml de docDock; en su lugar, agregue/edite HTML en: `/themes/docdock/layouts/partials/flex/body-before-content.html`
- **Left Menu**: `/themes/docdock/layouts/partials/flex/menu.html`
- **Footer Navigation**: `/themes/docdock/layouts/partials/flex/body-after-content.html`
- **Metadata Box**: `/themes/docdock/layouts/partials/flex/body-after-content.html`

## Ayuda: el CSS no carga

Un desafío con Hugo es que un parámetro clave en la compilación es la variable `baseURL`. Si el contenido se carga pero el CSS no, probablemente sea un problema con la configuración de `baseURL`.

Puede cambiar el `baseURL` al generar el contenido en lugar de cambiar el archivo config.toml. El ejemplo siguiente minificará el CSS y JS, establecerá el baseURL en la URL de producción .org y copiará los resultados al directorio `public`.

`hugo --minify --baseURL "https://workshops.nuevofoundation.org/"`

## Consejos y trucos

- **Ignorar public:** Por defecto, ejecutar `hugo` sin parámetros generará el sitio en el directorio public. Asegúrese de no agregar el directorio public al control de versiones (ya está en .gitignore).
- **Menú izquierdo:** Puede ocultar contenido del menú izquierdo estableciendo metadatos en el archivo `hidden: true` (¡como el index.md de este taller!)
- **Partials:** Para componentes reutilizables en una página, cree un nuevo partial bajo `/themes/docdock/layouts/partials/flex/`.