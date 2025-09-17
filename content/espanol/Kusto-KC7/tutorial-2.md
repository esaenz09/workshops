---
title: "Tutorial 2: New Employee Orientation"
draft: false
weight: 10
---
{{%showanswer "DISCLAIMER: All domains, data, and names used in this document, website, or any other materials are fictitious ... (cont.)"%}}
*AVISO LEGAL: Todos los dominios, datos y nombres utilizados en este documento, sitio web o en cualquier otro material son ficticios y han sido creados únicamente con fines ilustrativos y educativos. No representan a personas, empresas u organizaciones reales.*

*Este documento, sitio web o cualquier otro material, incluidos pero no limitados a textos, imágenes, gráficos, logotipos y software, se proporcionan "tal cual" sin garantía de ningún tipo, ya sea expresa o implícita, incluidas pero no limitadas a las garantías implícitas de comerciabilidad y aptitud para un propósito particular.*

*En ningún caso los creadores u propietarios de este documento, sitio web o cualquier otro material serán responsables de ningún daño, incluidos pero no limitados a daños directos, indirectos, especiales, incidentales o consecuentes, que surjan o estén relacionados con el uso o la imposibilidad de usar este documento, sitio web o cualquier otro material, incluso si se les ha advertido de la posibilidad de tales daños.*

*Los creadores u propietarios de este documento, sitio web o cualquier otro material se reservan el derecho de realizar cambios en el contenido en cualquier momento y sin previo aviso.*

*Al acceder o utilizar este documento, sitio web o cualquier otro material, usted acepta estar sujeto a los términos y condiciones establecidos en este aviso legal. Si no está de acuerdo con estos términos y condiciones, no debe acceder ni utilizar este documento, sitio web ni cualquier otro material.* 
{{%/showanswer%}}

## Introducción: Bienvenido a EnvolveLabs

¡Bienvenido a EnvolveLabs Corporation! 🥳 Hoy es tu primer día como Analista Junior del Centro de Operaciones de Seguridad (SOC) en nuestra empresa. Tu responsabilidad principal es defender a EnvolveLabs y a sus empleados frente a actores cibernéticos maliciosos.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/EnvolveLabLogo.png?raw=true" alt= “” width="50%" height="value">

EnvolveLabs es una startup de tecnología médica con sede en los Estados Unidos que fue fundada en 2012. Nuestra misión es desarrollar un nuevo tipo de tecnología de vacunas flexibles que cubra muchas cepas virales diferentes y ofrezca una inmunidad duradera. Esto eliminaría la necesidad de recibir refuerzos en intervalos regulares y haría que las vacunaciones sean más accesibles. Nuestra investigación inicial ha demostrado que esta tecnología es altamente efectiva: planeamos comenzar la producción en el primer trimestre de 2024.

EnvolveLabs cuenta con una serie de socios clave que contribuyen al éxito de nuestro negocio. Por ello, esperamos que nuestros empleados mantengan comunicación regular con estos socios clave:

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/Envolve1.png?raw=true" alt= “” width="60%" height="value">

Hasta ahora, nos hemos centrado intensamente en la investigación médica y en cumplir los objetivos de producción. Pero, a medida que nuestro trabajo se vuelve más importante y exitoso, hemos visto la necesidad de invertir más en esfuerzos de ciberseguridad. ¡Por eso te hemos contratado!

Como todas las buenas empresas, EnvolveLabs recopila datos de registros (logs) sobre la actividad que realizan sus empleados en la red corporativa. Estos registros de auditoría de seguridad se almacenan en Azure Data Explorer (ADX), un servicio de almacenamiento de datos en Azure (la nube de Microsoft). Utilizarás Kusto Query Language (KQL) para analizar varios tipos de registros de seguridad. Al examinar estos registros, puedes ayudarnos a determinar si estamos siendo objetivo de actores maliciosos.
 - Puedes encontrar la documentación completa sobre consultas KQL para ADX aquí:
 https://docs.microsoft.com/en-us/azure/data-explorer/kusto/query/tutorial?pivots=azuredataexplorer

### Base de datos de EnvolveLabs

La base de datos EnvolveLabs_Analysis contiene ocho tablas. Las tablas contienen muchas filas de datos similares. Para los registros de seguridad, una sola fila típicamente representa una única acción realizada por un empleado o un dispositivo en la red en un momento determinado.

Actualmente tenemos ocho tipos de datos de registro. Como verás en ADX, cada tipo de registro corresponde a una tabla que existe en la base de datos EnvolveLabs_Analysis:

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/Envolve3.png?raw=true" alt= “” width="70%" height="value">



{{< notice note >}}
🎯**Punto clave – datos Over the Horizon (OTH):** Una de las tablas mencionadas arriba no es como las demás – **PassiveDns**. En lugar de ser un registro de seguridad interno, **PassiveDns** es una fuente de datos que hemos comprado a un proveedor externo. No toda la actividad cibernética maliciosa ocurre dentro de nuestra red corporativa, por lo que a veces dependemos de datos de otras fuentes para completar nuestras investigaciones. {{< /notice >}}

Aprenderás más sobre cómo usar cada uno de estos conjuntos de datos en un momento. Primero, vamos a ejecutar algunas consultas para que puedas practicar usando KQL y ADX, manteniéndolo claro para principiantes.