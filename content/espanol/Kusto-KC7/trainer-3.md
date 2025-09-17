---
title: "T3: Event Schedule & Logistics"
draft: false
weight: 28
---
{{< alert theme="info" >}}
## Schedule
{{< /alert >}}

*[PREREQ, 10 min] Obtener acceso al clúster y añadirlo a ADX*

### Parte 1: Entendiendo el Entorno [1.5 hrs]

[5 min] Introducción a Threat Intel    
     - Mencionar brevemente herramientas y técnicas de atribución     
     - Diamond Model     
     - Kill Chain     

[20 min] Kusto Query Language (KQL) 101     
     - Introducir tablas, comandos y la sintaxis de KQL en el navegador de ADX     
      - where (has, contains, has_any, ==, etc…)     
      - count     
      - take     
      - let     

[10 min] Cómo agrupar actividad observada del adversario 
 - ¿Cómo decides si el siguiente elemento está asociado con tu actor? 
 - Mapear el conocimiento del actor al Diamond Model 
 - ¿Cómo sabes cuándo has terminado? 
 - Riesgos al agrupar (misaatribución)    

[45 min] Escenario 1: Introducción a la investigación cibernética
 - Investigar actividad maliciosa (p. ej., amenaza por correo electrónico)
 - Usar Azure Data Explorer (ADX) para analizar datos de registros de seguridad
 - Aplicar los fundamentos de KQL para responder preguntas concretas usando datos
 - Pivotar entre múltiples conjuntos de datos

[10 min] Informe de cierre 
 - Revisar brevemente cómo pivotar hasta las respuestas

### Descanso [10 min]
 
### Parte 2: Atrapar al Hacker [1.5 hrs Incluye Una Actividad Extra]

[5 min] Introducción y visión general del taller 
 - Herramientas y técnicas adicionales de Threat Intelligence (TI) y threat hunting para compartir antes de volver a la práctica

[30 min] Escenario 2: Atrapar al Hacker
 - Publicar el scoreboard e introducir el escenario
 - Facilitar tiempo libre de búsqueda
 - Monitorizar el chat

[10 min] Informe de cierre
 - Seleccionar algunas preguntas para mostrar el camino hacia la solución

*(Elija una actividad adicional para terminar la sesión si el tiempo lo permite)*    

{{%showanswer "Option 1: Phishy Activity"%}}	
**Opción 1**         
[5 min] Bono 1: Actividad Phishy

[30 min] Escenario 3: Hackers enviando documentos con malware
 - Tiempo libre para buscar

[10 min] Informe de cierre y cierre de la sesión {{%/showanswer%}}

{{%showanswer "Option 2: Truth or Misinformation"%}}	
**Opción 2**         
[5 min] Introducir análisis de blogs *(para audiencias más avanzadas)*

[30 min] Escenario 3: Verdad o desinformación
 - Tiempo libre para investigar y analizar el blog

[10 min] Informe de cierre y cierre de la sesión
{{%/showanswer%}}

{{%showanswer "Option 3: Security Jeopardy"%}}	
**Opción 3**         
[5 min] Introducir Security Jeopardy 
[30 min] Jugar
 - Depende del instructor decidir el formato. Se puede hacer que los estudiantes jueguen en el Scoreboard en sus ordenadores y poner un temporizador para ver quién tiene más puntos al final; esto sería un quiz con acceso a internet. O usar un generador de jeopardy para introducir preguntas para una audiencia más conocedora; ten en cuenta que las otras partes de este taller no enseñan ya estos términos *(es mejor jugar con una audiencia que tenga conocimientos previos de términos de ciberseguridad en una sesión en vivo)*.

[10 min] Informe de cierre y cierre de la sesión
{{%/showanswer%}}



{{< alert theme="success" >}}
## Logistics
{{< /alert >}}

### Lista de verificación

**Esto es todo lo que necesitarán tus estudiantes:**   
* Un ordenador o laptop (no tiene que ser especialmente potente)   
* Una buena conexión a Internet   
* Una cuenta de Microsoft   
    * Puede ser una cuenta personal hotmail u outlook    
    * O una cuenta de Office365 proporcionada por la escuela    
    * *Nota: Si la escuela u organización no permite el acceso a Azure Data desde el tenant de la empresa, necesitarás una solución alternativa, como proporcionar una cuenta específica para el evento que usen los participantes*     

**Aquí hay algunas cosas que también podrías necesitar:**   
* Versiones impresas en papel de la guía de formación (hemos comprobado que    
  los participantes tienden a trabajar mejor con una guía en papel)    
* Un proyector o pizarra interactiva para resolver problemas en grupo    
* Snacks o golosinas — a todos les encantan :)    

### Configuración del Scoreboard

Para acceder al KC7 scoreboard, ve a: https://kc7.azurewebsites.net.
 Necesitarás iniciar sesión con las credenciales que te enviaron por correo después de rellenar el formulario para alojar una sesión. Si no estás alojando una sesión, puedes crear una cuenta para iniciar sesión.

Si estás gestionando una sesión, ya deberías estar añadido a la partida de juego para tu grupo. La verás en tu panel al iniciar sesión. Para unirte a la sesión, sólo haz clic en el botón "join this game".

También necesitarás añadir preguntas o retos para que los participantes del juego respondan y obtengan puntos. Para ello:

* Asegúrate de haber iniciado sesión como administrador de tu sesión
* Busca la lista de preguntas que corresponde con la guía de formación que estás usando
* Selecciona el conjunto de preguntas en el menú desplegable

### Recursos adicionales

KC7 Github Repo: https://github.com/kkneomis/kc7       
KC7 Website: https://kc7cyber.com/#demos       

; manténlo claro para principiantes. 
        Conserva términos técnicos, sintaxis de código y formato. Traduce sólo los comentarios que explican conceptos.
        Adapta las referencias culturales apropiadamente. No traduzcas la clave de título del encabezado; no traduzcas el HTML de imágenes.