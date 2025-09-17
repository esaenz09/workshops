---
title: "How the site is built"
date: 2020-07-29T14:08:32-07:00
draft: false
weight: 1
---

# Cómo está construido el sitio

El contenido del subdominio de workshops se crea usando el tema [DocDock](https://docdock.netlify.com/) para Hugo. [Hugo](https://gohugo.io) es un generador de sitios estáticos con varias ventajas:

1. **Autores de contenido** pueden centrarse en el contenido usando markdown y no en la implementación técnica del sitio o el estilo CSS/páginas. Los workshops se añaden *automágicamente* al índice de la izquierda y a la página principal de workshops. Hugo funciona muy bien localmente (p. ej.: en un avión), y Hugo es el generador de sitios estáticos más rápido, construyendo todo el sitio de workshops en <2 segundos.  
2. **Estudiantes** se benefician de una experiencia de usuario (UX) consistente entre los workshops, accesibilidad integrada, localización, diseño responsive que abarca desde móvil hasta escritorio, enlaces automáticos al repositorio de GitHub y un rendimiento global rápido del sitio usando la CDN de Azure.  
3. **Nuevo Dev Team** se beneficia de la capacidad de crear y personalizar páginas de workshop, incluidas plantillas de página personalizadas, [controles de página integrados para alertas, notas, botones, advertencias y más](https://workshops.nuevofoundation.org/guidelines/formatting/), controles personalizados (p. ej.: el encabezado de Nuevo), interactividad mediante iframes, metadatos personalizados, enlaces automáticos entre páginas, tematización de páginas, creación automática del mapa del sitio, iconos integrados y automatización integrada usando GitHub Actions y Azure DevOps para compilación/despliegue.