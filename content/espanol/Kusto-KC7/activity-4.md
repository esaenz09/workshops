---
title: "Activity 4: Catch the Hacker"
draft: false
weight: 16
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/HjKkQVH5-rQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

{{< notice note >}}Esta sección es mucho más corta; solo vamos a explicar el escenario y dejarte tiempo libre para investigar. Puedes tomar todo el tiempo que desees en esta parte, pero en sesiones en vivo generalmente damos a los participantes 30-40 minutos antes de continuar.

- **Asegúrate de usar la base de datos SecurityLogs**
- **Envía tus respuestas al desafío "Introducing the Hackers" en el Scoreboard**

#### **¡Buena búsqueda!**{{< /notice >}}

### Presentando a los hackers


Ahora que has completado tu ronda inicial de entrenamiento, ¡estás listo para trabajar tu primer caso en el SOC!

Un investigador de seguridad tuiteó que el dominio *“immune[.]tech”* estaba siendo usado por hackers. Al parecer los atacantes están enviando correos de phishing para robar credenciales (inicios de sesión, contraseñas, etc.) desde dentro de este dominio.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/CTF1.png?raw=true" alt= “CTF1” width="value" height="value">

{{< alert theme="warning" >}}
⚠️NOTA: Es un protocolo de seguridad común usar el formato immune[.]tech o domain[.]com al mencionar enlaces potencialmente maliciosos en línea. Agregar estos corchetes alrededor del punto evita la creación de un enlace clicable. Al buscar en los registros, asegúrate de quitar los corchetes del nombre de dominio. {{< /alert >}}

Según la investigación OSINT que realizaron tus colegas, este dominio podría estar siendo utilizado como parte de una campaña de phishing con las siguientes etapas:

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/CTF2.png?raw=true" alt= “CTF2” width="value" height="value">

{{< notice note >}}🎯**Punto clave – Inteligencia de Fuentes Abiertas (OSINT)**: Los investigadores y analistas de seguridad a menudo usan datos gratuitos y de acceso público, ¡como Twitter! A estos datos públicos los llamamos OSINT, y pueden ser una excelente manera de obtener pistas investigativas. Como con todas las fuentes públicas en internet, debes seguir cualquier pista de OSINT con un análisis riguroso en lugar de confiar ciegamente en la fuente.{{< /notice >}}
{{< alert theme="success" >}}
🤔 **Considera las siguientes preguntas relacionadas con esta pista para ayudarte a pensar durante la caza. Algunas pistas están incluidas en las preguntas a continuación:** 

{{%showanswer "Question 1"%}}
*¿A qué usuarios de nuestra organización se les enviaron correos que contenían el dominio immune.tech?*

🤫 **Pista**: Prueba el siguiente comando e inserta el nombre de dominio en cuestión.
```
Email
| where link contains '[insert domain name]'
``` 
{{%/showanswer%}}

{{%showanswer "Question 2"%}}	
*¿Bloqueamos alguno de los correos que contenían ese dominio? ¿Quién recibió realmente uno de esos correos?*     

🤫 **Pista**: El campo “accepted” en la tabla Email te indica si el correo fue o no bloqueado. Los correos bloqueados mostrarán false.* {{%/showanswer%}}

{{%showanswer "Question 3"%}}	
*¿Qué otros dominios compartieron las mismas IP que immune.tech? ¿Puedes encontrar la lista completa de dominios asociados con este actor basándote en datos de PassiveDns?* 

🤫 **Pista**: Puedes usar el operador in para comprobar múltiples valores en un campo. Ej.: where field in (“x”, “y”, “z”)* {{%/showanswer%}}

{{%showanswer "Question 4"%}}
*¿Qué direcciones de correo usaron los atacantes para enviar estos dominios?* 

🤫 **Pista**: Fíjate quién aparece listado en la columna "sender" para los correos que ahora sabes contienen asuntos y enlaces sospechosos. {{%/showanswer%}}

{{%showanswer "Question 5"%}}
*¿Algún usuario hizo clic en los enlaces de los correos de phishing?* 

🤫 **Pista**: Revisa los logs de archivos, eventos de procesos y/o el historial de navegación de los dispositivos y cuentas asociadas con los usuarios que recibieron el correo malicioso para ver si hay evidencia de actividad extraña que indique que hicieron clic en el enlace. {{%/showanswer%}}

{{%showanswer "Question 6"%}}
*¿Algún usuario tuvo sus credenciales robadas? ¿Cómo lo sabes?* 

🤫 **Pista**: Para que sus credenciales sean robadas, un usuario tendría que navegar al sitio de recolección de credenciales e ingresar su usuario y contraseña. Después de esto, el actor podría intentar iniciar sesión en la cuenta del usuario usando las credenciales robadas. Puedes encontrar detalles sobre la actividad de inicio de sesión en la tabla **AuthenticationEvents**. {{%/showanswer%}}

{{%showanswer "Question 7"%}}
*¿Algún usuario tuvo contenido exfiltrado (robado) de su buzón? ¿Cómo lo sabes? ¿Qué riesgo representa para la empresa que ese contenido haya sido robado?* {{%/showanswer%}}
{{< /alert >}}