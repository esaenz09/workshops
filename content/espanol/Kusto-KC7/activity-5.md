---
title: "Bonus 1: Phishy Activity"
draft: false
weight: 20
---


## Hackers Envían Documentos con Malware

After digging for a bit on the phishing activity, you come across another tweet from a threat intelligence vendor SolitaryStrike:

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/Bonus1.png?raw=true" alt= “Bonus1” width="value" height="value">


{{< notice note >}}
🤔 Usa el tweet para comenzar tu rastreo. Deja que las preguntas te ayuden a pivotar entre los datos para entender qué está pasando.     
- Envía tus respuestas al reto "Hackers Sending0 Malware Docs" en el Scoreboard en https://kc7cyber.azurewebsites.net/ para recibir retroalimentación y ganar puntos. Las preguntas abajo se reflejan en el Scoreboard para esta sección. **No existe una clave maestra de respuestas para esta sección aparte del Scoreboard.**
- **Asegúrate de usar la base de datos SecurityLogs para este ejercicio.**{{< /notice >}}
{{< alert theme="success" >}}
🤔 **Considera las siguientes preguntas relacionadas con este tip para ayudarte a pensar durante el hunt. Algunas pistas están incluidas en las preguntas abajo:** 

{{%showanswer "Question 1"%}}	
*¿Cuántos correos electrónicos contenían el dominio notice[.]io?* 

🤫**Pista:** ¿En qué tabla de la base de datos SecurityLogs podría haber una columna que contenga evidencia de este sitio web/dominio sospechoso? {{%/showanswer%}}

{{%showanswer "Question 2"%}}	
*¿Qué dirección de correo electrónico envió el dominio notice[.]io?* {{%/showanswer%}}

{{%showanswer "Question 3"%}}	
*¿Cuál fue la línea de asunto de los correos que contenían el dominio notice[.]io?* {{%/showanswer%}}

{{%showanswer "Question 4"%}}	
*¿Cuál es el nombre del usuario que hizo clic en el enlace notice[.]io?* {{%/showanswer%}}

{{%showanswer "Question 5"%}}	
*¿En qué marca temporal (timestamp) el usuario anterior descargó el archivo: "Critical_Security_Path.docx"?*    

🤫**Pista:** Los archivos que se crean en los dispositivos de los empleados se capturan en el log FileCreationEvents. Intenta buscar allí para ver qué empleados descargaron este archivo. {{%/showanswer%}}

{{%showanswer "Question 6"%}}	
*¿Cuántos correos fueron enviados a tu organización el 9 de enero por usuarios de wesellbeakers.com?* 

🤫**Pista:** Si no recuerdas el formato de fecha/hora para los registros de Email, haz otra consulta 'take 10' y observa. Te ayudará al escribir la consulta para esta pregunta. {{%/showanswer%}}

{{%showanswer "Question 7"%}}	
*¿Qué otros dominios están alojados en las mismas IPs que notice[.]io?* {{%/showanswer%}}

{{%showanswer "Question 8"%}}	
*¿Qué dirección de correo se observa enviando correos que contienen uno de los dominios identificados en la pregunta 7?* {{%/showanswer%}}

{{%showanswer "Question 9"%}}	
*¿Cuántos usuarios descargaron los archivos observados en los correos de la pregunta 8?* {{%/showanswer%}}

{{%showanswer "Question 10"%}}	
*Uno de los archivos observados en la Pregunta 9 - **IMPORTANT_INSTRUCTIONS.pptx** - apareció en dos correos separados. ¿Cuáles son las líneas de asunto de esos correos?* {{%/showanswer%}}

{{%showanswer "Question 11"%}}	
*¿Qué dirección de pharmasupplies.org comprometida se utilizó para enviar un enlace a scanverify.com?* {{%/showanswer%}}

{{%showanswer "Question 12"%}}	
*¿A cuántas IPs ha resuelto scanverify.com?* {{%/showanswer%}}

{{%showanswer "Question 13"%}}	
*Considera la dirección de correo que encontraste en la pregunta 11. ¿A qué otro dominio envió correos esta dirección?* {{%/showanswer%}}

{{%showanswer "Question 14"%}}	
*¿Cuál es el nombre del archivo alojado en scanverify.com?* {{%/showanswer%}}

{{%showanswer "Question 15"%}}	
*¿Qué archivo .pptx se usó para apuntar a Gerald Kempinski y Kenny Salcido?* {{%/showanswer%}}

{{%showanswer "Question 16"%}}	
*¿Qué IP del actor se usó para buscar en el sitio de EnvolveLabs el término "helpdesk ticket system"?* {{%/showanswer%}}

{{%showanswer "Question 17"%}}	
*¿Cuántos correos en total envió este actor a tu organización?* {{%/showanswer%}}

{{%showanswer "Question 18"%}}	
*¿Qué archivo .dll fue colocado en una máquina víctima poco después de que el usuario descargara el zip malicioso: **EnvolveLabs_Research_Tool.7z**?*

🤫**Pista:** Los archivos creados en los dispositivos de los empleados se capturan en el log FileCreationEvents. Intenta buscar allí para ver qué empleados descargaron este archivo. {{%/showanswer%}}

{{%showanswer "Question 19"%}}	
*¿Qué comando de reconocimiento de seis letras se ejecutó en la máquina del usuario que cargó el implant anterior?*

🤫**Pista:** Intenta enfocarte en un dispositivo particular que descargó el archivo EnvolveLabs_Research_Tool.7z. Luego, revisa tanto los logs FileCreationEvents como ProcessEvents para encontrar nuevos archivos y procesos creados alrededor del momento en que se descargó el archivo.{{%/showanswer%}}

{{%showanswer "Question 20"%}}	
*Un archivo malicioso 'infector.exe' se observa realizando acciones sospechosas en múltiples dispositivos. ¿Qué process_commandline asociado con este archivo se está usando para persistencia en los dispositivos?*

🤫**Pista:** Los actores establecen persistencia para poder volver más tarde y realizar tareas manuales (actividad hands-on-keyboard) dentro de la red de tu empresa. Intenta buscar sistemas que creen conexiones a dominios/IPs externos o comportamientos inusuales como la creación de tareas programadas (scheduled tasks). {{%/showanswer%}}
{{< /alert >}}