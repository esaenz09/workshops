---
title: "Tutorial 1: Intro to Threat Intelligence"
draft: false
weight: 6
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/F6qFmiV6Alc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

{{< notice note >}} A medida que avanzas en este taller, notarás que cada página con un video duplica la lección en forma de video y por escrito. Puedes seguir una u otra según el tipo de aprendiz que seas.{{< /notice >}}
## ¿Qué es la Inteligencia de Amenazas?

**Analistas de Inteligencia de Amenazas**:

{{<icon name="user" size="large">}} Aprenden sobre los adversarios ... y comparten conocimientos con socios del sector público/privado

{{<icon name="time" size="large">}} Hacen seguimiento de los adversarios a lo largo del tiempo ... para entender el panorama de amenazas cambiante

{{<icon name="lock" size="large">}} Implementan defensas ... y trabajan con equipos de desarrollo de productos para proteger a los clientes

Los datos por sí solos no equivalen a inteligencia. Los registros de seguridad por sí mismos no te dicen nada significativo hasta que no los procesas. Una vez que un analista de inteligencia de amenazas procesa los datos y la información, con el contexto de los adversarios que sigue y el contexto del cambio en el panorama de amenazas, puede comenzar a construir una historia y una línea de tiempo de lo que pudo haber ocurrido. Para entender qué significan esas amenazas, por qué ocurrieron y cómo han afectado a su empresa ... eso es la verdadera inteligencia de amenazas.

## ¿Qué es el Cyber Kill Chain?

El Cyber Kill Chain, desarrollado originalmente por Lockheed Martin, es un marco para identificar y prevenir ataques cibernéticos. Este marco identifica 7 pasos que los adversarios deben completar para lograr su objetivo [^1].
[^1]: https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html

<img src= "https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/photo/cyber/THE-CYBER-KILL-CHAIN-body.png.pc-adaptive.1280.medium.png" alt= “CyberKillChain” width="60%" height="value">


## Comprendiendo el Diamond Model

El Diamond Model of Intrusion Analysis proporciona un método para analizar las características de los ataques cibernéticos. Este modelo enfatiza las relaciones entre 4 componentes: **el adversario, las capacidades, la infraestructura y las víctimas**. La teoría en la que se basa es que para cada ataque cibernético existe "un **adversario** que da un paso hacia un objetivo previsto usando una **capacidad** sobre una **infraestructura** contra una **víctima** para producir un resultado" [^2].
[^2]: https://www.recordedfuture.com/diamond-model-intrusion-analysis 

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/diamondmodel.png?raw=true" alt= “DiamondModel” width="40%" height="value">

## ¿Qué es KC7?

Esto nos lleva a por qué elegimos llamar a este juego KC7; porque ayuda a guiar a las personas a través de las 7 etapas del Cyber Kill Chain descritas arriba.

**KC7 es un juego diseñado para enseñar a las personas cómo aplicar conocimientos de ciberseguridad y desarrollar habilidades de análisis usando datos realistas.** Es una simulación de análisis de ciberseguridad única e inmersiva que fue desarrollada por expertos en seguridad del Threat Intelligence Center de Microsoft (MSTIC), un equipo que se centra en rastrear a los actores cibernéticos más sofisticados del mundo. Lo mejor de estos datos es que son ficticios y generados por un script de Python, lo que significa que los participantes pueden aprender técnicas reales sin los peligros de manejar datos privados. Esta formación ofrece a los participantes la oportunidad de aprender y aplicar habilidades de análisis de amenazas cibernéticas mientras defienden una empresa simulada de hackers. 

{{< alert theme="info" >}} Ahora que hemos cubierto algunos temas de inteligencia de amenazas, sigamos adelante. No te preocupes si no lo entiendes todo de inmediato; estos temas serán más fáciles de comprender más adelante en la formación. {{< /alert >}}
; mantenerlo claro para principiantes. 
        Preservar términos técnicos, sintaxis de código y formato. Traducir sólo los comentarios que expliquen conceptos.
        Adaptar las referencias culturales de forma apropiada. No traduzca la clave de encabezado title; no traduzca el html de las imágenes