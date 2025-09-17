---
title: "Activity 2: Threat Intel Game"
draft: false
weight: 8
---


<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/ETcVXoS_Ytk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>


{{< rawhtml >}}

<SCRIPT language="JavaScript"
        type="text/javascript">
<!--
// 
// Documentación:
//   http://chami.com/tips/javascript/
//
function checkAnswer(quizForm,
                     theAnswer,
                     urlRight,
                     urlWrong)
{
  var s = "?";

  // recorrer las "opciones actuales"
  // para encontrar la opción seleccionada.
  // los botones radio que apuntan a las opciones
  // deben llamarse "cc"
  // cambiar si es necesario
  //
  var i = 0;
  for(;i<quizForm.elements.length;i++)
  {
    if(("cc" ==
        quizForm.elements[i].name) &&
       (quizForm.elements[i].checked))
    {
      s = quizForm.elements[i].value;
    }
  }

  // no se seleccionó ninguna opción
  //
  if("?" == s)
  {
    alert("Please make a selection.");
    return false;
  }

  // comprobar si tenemos la
  // opción correcta seleccionada
  //
  if(s == theAnswer)
  {
    alert("'"+s+"' is correct!");
    if(urlRight)
    {
    document.location.href = urlRight;
    }
  }
  else
  {
    alert("'"+s+"' is incorrect.");
    if( urlWrong )
    {
    document.location.href = urlWrong;
    }
  }

  // devolver "false" para indicar que no
  // se debe enviar el formulario.
  // cambiar esto a "true" si la acción del formulario
  // es válida,
  // es decir, apunta a un script CGI válido
  //
  return false;
}
//-->
</SCRIPT>

{{< /rawhtml >}}



{{< alert theme="success" >}}La mejor manera de completar esta sección es reproducir el video mientras sigues la página que aparece a continuación.{{< /alert >}}

### ¿Qué es la atribución?

Un tema clave en el mundo de la ciberseguridad con el que te encontrarás se llama **atribución**. La atribución en ciberseguridad se refiere al proceso de rastrear, identificar y, en general, atribuir la responsabilidad al perpetrador de un ciberataque. Los ciberataques, también conocidos comúnmente como *hacking*, son intentos por parte de un adversario de obtener acceso a sistemas con el propósito de alterar, robar, destruir o exponer información. Ejemplos de métodos para llevar a cabo un ciberataque incluyen:
- **Malware** - Abreviatura de software malicioso; es cualquier código creado con la intención de hacer daño, como un virus o un gusano.
- **Phishing** - Un ataque que utiliza correo electrónico, mensajes de texto (SMS) o redes sociales para incitar a una víctima a compartir información sensible o a descargar un archivo malicioso; es similar al “catfishing”.
- **Ransomware** - Código malicioso destinado a bloquear a las víctimas fuera de sus propios sistemas con el fin de exigir un rescate, usualmente dinero, a cambio de recuperar el acceso a sus sistemas o datos bloqueados.
- **Password Spray** - Un atacante obtiene una lista de nombres de usuario y luego intenta iniciar sesión con la misma contraseña en todos los usuarios, repitiendo el proceso con nuevas contraseñas hasta obtener acceso al sistema.

### Desafíos de la atribución

Aunque es una parte clave de la ciberseguridad, la atribución puede ser difícil de realizar, incluso para expertos en ciberseguridad. Los expertos a menudo deben llevar a cabo extensas investigaciones forenses y analizar gran cantidad de datos buscando formas de probar quién podría ser responsable de los ataques. Algunas cosas que los expertos analizan para ayudar en esto son:
- **Datos históricos** - ¿Existen patrones repetidos usados en múltiples ciberataques a lo largo del tiempo que podrían indicar qué actor(es) maliciosos podrían estar detrás?
- **Intención o motivos** - ¿Hay ataques que apuntan específicamente a instituciones educativas, por ejemplo? ¿Podría un ciberataque coincidir con un conflicto político públicamente observable entre países que no pueden permitirse ser vistos disparando misiles, enviando tropas militares u ocupándose de lo que se llama **guerra cinética** contra otro país?
- **Patrón geográfico del ataque** - ¿Se están atacando predominantemente organizaciones de un país en particular? Contrariamente, ¿una entidad está atacando organizaciones en todo el mundo EXCEPTO un país... potencialmente el suyo propio?

El nivel de dificultad de la atribución cibernética la convierte en un método atractivo de ataque para grupos con el conocimiento, los recursos y la motivación para intentarlo mientras ocultan trazas de su implicación. Con esto en mente, nuestra misión es ayudar a formar a la próxima generación de Defensores Cibernéticos para combatir los ciberataques. Por difícil que pueda ser, este tipo de trabajo tiene un impacto en el mundo real. Consulta esta historia a continuación que demuestra el nivel de impacto que pueden tener los Defensores Cibernéticos:
- Exposing POLONIUM activity and infrastructure targeting Israeli organizations: https://vulners.com/mssecure/MSSECURE:A2F131E46442125176E4853C860A816C 

### Clasificaciones de adversarios

Usamos 3 categorías principales para clasificar a los adversarios: **hacktivistas, ciberdelincuentes y actores patrocinados por estados**.

Hacktivistas son personas que no están afiliadas a un gobierno específico y normalmente no actúan por dinero. Creen apasionadamente en algún ideal y usan ciberataques para promover su misión.
Características clave
- Hackean para difundir un ideal
- Buscan cambios políticos o sociales
- No necesariamente son los más avanzados técnicamente
- Ej.: Cult of the Dead Cow / Anonymous

Ciberdelincuentes hackean con la motivación principal de obtener ganancias financieras.
Características clave
- Motivados por el dinero
- Objetivos indiscriminados
- Ransomware / Estafas empresariales / Hack and Leak
- El nivel de organización varía
- Lobos solitarios y mafias organizadas

Patrocinados por estados son actores que operan en nombre de su gobierno. Muchos gobiernos financian y dirigen grupos cibernéticos para que hackeen en línea con los objetivos del gobierno, que pueden ser políticos, financieros, relacionados con la defensa, etc.
- Patrocinados o afiliados al gobierno
- Altamente financiados
- Altamente motivados
- Selectivos en sus objetivos
- Visión a largo plazo




-----------------------------------------------------


### Es hora de jugar a Whodunit (¿Quién lo hizo?), donde presentamos algunos escenarios y tú intentas practicar la atribución.

<br/>

#### Pregunta 1:
<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/WhodunitQ1.png?raw=true" alt= “WhodunitQ1” width="80%" height="value">

#### ¿Qué tipo de adversario crees que lo hizo?


<FORM method="POST"
      onSubmit="return checkAnswer(this,'C');"
>

<INPUT TYPE="RADIO" VALUE="A" NAME="cc">
A. Hacktivista<BR>

<INPUT TYPE="RADIO" VALUE="B" NAME="cc">
B. Ciberdelincuente<BR>

<INPUT TYPE="RADIO" VALUE="C" NAME="cc">
C. Patrocinado por un Estado<BR>

<INPUT TYPE="SUBMIT" VALUE="Enviar respuesta">

</FORM>
<br/>

#### Pregunta 2:
<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/WhodunitQ2.png?raw=true" alt= “WhodunitQ2” width="80%" height="value">

#### ¿Qué tipo de adversario crees que lo hizo?


<FORM method="POST"
      onSubmit="return checkAnswer(this,'B');"
>

<INPUT TYPE="RADIO" VALUE="A" NAME="cc">
A. Hacktivista<BR>

<INPUT TYPE="RADIO" VALUE="B" NAME="cc">
B. Ciberdelincuente<BR>

<INPUT TYPE="RADIO" VALUE="C" NAME="cc">
C. Patrocinado por un Estado<BR>

<INPUT TYPE="SUBMIT" VALUE="Enviar respuesta">

</FORM>

<br/>

#### Pregunta 3:
<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/WhodunitQ3.png?raw=true" alt= “WhodunitQ3” width="80%" height="value">

#### ¿Qué tipo de adversario crees que lo hizo?


<FORM method="POST"
      onSubmit="return checkAnswer(this,'C');"
>

<INPUT TYPE="RADIO" VALUE="A" NAME="cc">
A. Hacktivista<BR>

<INPUT TYPE="RADIO" VALUE="B" NAME="cc">
B. Ciberdelincuente<BR>

<INPUT TYPE="RADIO" VALUE="C" NAME="cc">
C. Patrocinado por un Estado<BR>

<INPUT TYPE="SUBMIT" VALUE="Enviar respuesta">

</FORM>


____________________

{{< alert theme="info" >}}Mira el video en esta página para escuchar más sobre por qué las respuestas son las que son, y para aprender detalles interesantes sobre los ejemplos de adversarios reales usados en este juego Whodunit. ¡Gracias por jugar! Pasemos a la siguiente sección.{{< /alert >}}; mantenerlo claro para principiantes. Preserva términos técnicos, sintaxis de código y formato. Traduce solo los comentarios que expliquen conceptos. Adapta las referencias culturales adecuadamente. No traduzcas la clave de encabezado "title"; no traduzcas el HTML de las imágenes.