---
title: "Bonus 2: Truth or Misinformation?"
draft: false
weight: 22
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/bGFhF22Lr9I" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

## Análisis del blog de ciberseguridad

Para este escenario, nos gustaría que revisaras la entrada del blog que aparece a continuación y veas si puedes encontrar evidencias en **SecurityLogs2** que apoyen o refuten la información publicada.

------------------------------------------------------
*[Inicio de la entrada del blog]*

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/blog1.png?raw=true" alt= “Blog1” width="value" height="value">


¿Qué es UnhelpfulDesk? 
 
Los implantes del malware UnhelpfulDesk son desplegados por archivos cuyos nombres se asemejan a funciones legítimas de TI, como actualizaciones de software o restablecimientos de contraseña, o a temas de investigación médica, como investigación sobre vacunas. Estos archivos se entregan a las víctimas mediante correos electrónicos maliciosos que contienen enlaces para descargar los archivos.  
 
 
UnhelpfulDesk Droppers
 
| Filename 	| Sha256     |
| --------------- | ------------------------------------------------------- |
|Thesis_on_vaccine.exe 	| 232568cb9c5d1b3698334c504b173e637826d 79074fb8fa23a54981578eb7dc9   |
|ResearchBibliographyGenerator.pptx 	| 6e4a6278077f310e69017dba9a173d9d27 eddec9236231e1717a475c26242ae6    |
|Software_Update.rar |	2f2e5f20a726e9710b9c5c7c681e66240f854acd 48107e5cd193d6133297b72f    |
|IT_PASSWORD_RESET_TOOL.rar |	fe04d68b163bbf432196c0d7bb184176a42606 30374c93c916cc6b52fc9855f7 |
 
Dropped Implants
 
|Filename 	| Sha256 |
| --- | --- | 
|updater.dll |	3666cb55d0c4974bfee855ba43d596fc6d10 baff5eb45ac8b6432a7d604cb8e9 | 
|updater.dll |	42a337bcec26df0130a11baf9e6017999385 1b88f1cabec52973f88774e903fb | 
|updater.dll |	ea05ff75fef906a60545129a7c5bea2956bf de63b8e714eb42db3ae50b99dec3 | 
|updater.dll |  370ce39ba328329ff16b5ede1079f6402e68 abceb34e65cb31883a3b3730b530 | 
|updater.dll |	e3970346ff7fcc3665f027d7f221968087f3 c42705f5799fbc1d2811ab1ca4ea | 
 
 
Nota: *Muestras de los archivos del implante UnhelpfulDesk detectadas por los investigadores de VulnerableArray están disponibles en VirusTotal.*
 
Una vez desplegado con éxito, el implante UnhelpfulDesk realiza reconocimiento mediante los siguientes comandos:
```
  ping 8.8.8.8    
  whoami    
  net user Administratr 
```
A continuación, el malware cifrará archivos en la máquina y exigirá un rescate para descifrarlos. La nota de rescate se descarga desde Pastebin como se muestra a continuación:
```
curl https://pastebin[.]com/HOW%20TO%20RECOVER%20YOUR%20FILES.txt 
```

Otros Indicadores de Compromiso (IOCs)
 
214.217.73[.]146     
65.69.253[.]41     
199.57.49[.]250     
install-notice[.]com      
remarkablevirus[.]tech        
noreply_info[@]hotmail.com      
vaccinejournal[@]yahoo.com 

*[Fin de la entrada del blog]*

-----------------------------------------------------

## Ahora depende de ti…

Nuestro Director de Seguridad de la Información (CISO) te ha pedido que evalúes este informe de VulnerableArray y determines si es preciso utilizando los registros de la base de datos **SecurityLogs2**.     

🤔  Mientras realizas tu evaluación, considera las siguientes preguntas:

{{< alert theme="success" >}}
*Pregunta 1. ¿Todos los indicadores reportados pertenecen al mismo conjunto de actividad? ¿Cómo lo sabes?*
 {{< notice note >}}
  Pista: Usa el Modelo Diamante (Adversario, Víctima, Infraestructura, Capacidades) para ayudarte a pensar en la agrupación de actividades distintas. Busca similitudes y diferencias en cada uno de los cuatro vértices del Modelo Diamante.  {{< /notice >}}
 
*Pregunta 2. El informe afirma que el malware UnhelpfulDesk tiene como objetivo final desplegar ransomware y cifrar archivos en un sistema infectado. ¿Estás de acuerdo con esta evaluación? ¿O ves evidencia de acciones u objetivos alternativos?*
 {{< notice note >}}
  Pista: Intenta buscar actividad relacionada con los indicadores basados en malware compartidos en el blog y luego identifica algunos sistemas comprometidos. ¿Ves actividad posterior al compromiso en alguno de estos sistemas que sea diferente del ransomware descrito en el blog? {{< /notice >}}
 
*Pregunta 3. ¿Qué errores analíticos, si los hubo, cometieron los autores del blog?* 
 {{< notice note >}}
  Pista: Algunos procesos se ejecutan automáticamente por el malware al ejecutarse. Otros procesos se ejecutan manualmente (mano en el teclado) por el operador después de que se establece el canal de comando y control. {{< /notice >}}
 
*Pregunta 4. ¿El malware UnhelpfulDesk es exclusivo del actor ITINIUM? ¿Cómo lo sabes?* 
 {{< notice note >}}
  Pista: Los implantes updater.dll parecen ser desplegados desde archivos con dos temas separados (TI e investigación). Piensa por qué podría ser así.  {{< /notice >}}
 
*Pregunta 5. ¿Hay múltiples actores apuntando a Envolve Labs? En caso afirmativo, ¿puedes describir las Tácticas, Técnicas y Procedimientos (TTPs) de cada uno? ¿En qué se parecen? ¿En qué difieren?* 
{{< notice note >}}
  Pista: Compara y contrasta el modelo diamante para cada uno de los grupos de actividad observados. {{< /notice >}}
 
*Pregunta 6. ¿De qué manera las brechas en la visibilidad pudieron haber contribuido a las conclusiones del autor o autores del blog? ¿Cómo podrían contribuir a tus propias evaluaciones analíticas?*
{{< /alert >}}

Mantén el contenido claro para principiantes.  
Preserva los términos técnicos, la sintaxis de código y el formato. Solo traduce las explicaciones conceptuales.