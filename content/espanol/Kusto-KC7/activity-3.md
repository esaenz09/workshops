---
title: "Activity 3: Kusto Query Language 101"
draft: false
weight: 12
---

<p style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/lAeRxuUN1IM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

{{< notice tip >}} Aquí queremos que abras el Scoreboard y el ADX viewer que usaste antes en ventanas separadas para completar los ejercicios restantes. Si no puedes o no quieres usar el Scoreboard, todas las preguntas de esta sección están listadas abajo.

*Recuerda que cualquier página con un video duplica la lección tanto en forma de video como escrita. Puedes seguir una u otra según el tipo de aprendiz que seas.* {{< /notice >}}

## KQL 101

**[Asegúrate de usar la base de datos SecurityLogs para este ejercicio.]**

Escribe la siguiente consulta en el área de trabajo para ver las primeras filas de la tabla **Employees**. Presiona “run” o “shift + enter” para ejecutar la consulta. Todos los bloques de código KQL para este taller estarán delimitados en gris como el siguiente.

```KQL
Employees
|   take 10
```

Esta consulta tiene varias partes. Tomémonos un momento para desglosarlas:

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL1.png?raw=true" alt= “KQL1” width="50%" height="value">

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL2.png?raw=true" alt= “KQL2” width="80%" height="value">

El operador <span style="color:red">**take**</span> es una herramienta poderosa que puedes usar para explorar filas en una tabla y, por lo tanto, comprender mejor qué tipo de datos se almacenan allí.

{{< notice note >}} 🎯**Punto clave – Qué hacer cuando no sabes qué hacer**: Siempre que te enfrentes a una tabla de base de datos desconocida, lo primero que deberías hacer es muestrear sus filas usando el operador <span style="color:red">**take**</span>. De ese modo, sabrás qué campos están disponibles para consultar y podrás intuir qué tipo de información podrías extraer de la fuente de datos. {{< /notice >}}

La tabla Employees contiene información sobre todos los empleados de nuestra organización. En este caso, podemos ver que la organización se llama “Envolve Labs” y el dominio es “envolvelabs.com”.

{{< alert theme="success" >}}
*Pregunta 1. 🤔 ¡Pruébalo tú mismo! Haz un <span style="color:red">**take**</span> 10 en todas las demás tablas para ver qué tipo de datos contienen.*{{< /alert >}}

Puedes escribir fácilmente múltiples consultas en la misma pestaña del área de trabajo. Para hacerlo, asegúrate de separar cada consulta con una línea vacía. Observa abajo cómo hemos separado las consultas para las tablas Employees, Email y OutboundBrowsing con líneas vacías en las líneas 3 y 6.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL3.png?raw=true" alt= “KQL3” width="value" height="value">

Cuando tienes múltiples consultas, es importante indicar a ADX cuál quieres ejecutar. Para elegir una consulta, simplemente haz clic en cualquier línea que forme parte de esa consulta. Una vez seleccionada, se resaltará en azul, como se ve en las líneas 4 y 5 arriba.

#### Encontrar “Cuánto”: El operador 'count'

Podemos usar <span style="color:red">**count**</span> para ver cuántas filas hay en una tabla. Esto nos dice cuánta información está almacenada.

```KQL
Employees
|   count
```
{{< alert theme="success" >}}
*Pregunta 2. 🤔 ¿Cuántos empleados hay en la empresa?*{{< /alert >}}

#### Filtrar datos con el operador 'where'

Hasta ahora, hemos ejecutado consultas que miran todo el contenido de la tabla. A menudo, en análisis de ciberseguridad, solo queremos ver datos que cumplen un conjunto de condiciones o criterios. Para lograr esto, aplicamos filtros a columnas específicas.

Podemos usar el operador <span style="color:red">**where**</span> en KQL para aplicar filtros a un campo particular. Por ejemplo, podemos encontrar a todos los empleados con el nombre “Linda” filtrando la columna name en la tabla **Employees**.

<span style="color:red">**where**</span> se escribe usando una estructura particular. Usa la tabla útil a continuación para entender cómo estructurar una sentencia <span style="color:red">**where**</span>.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL4.png?raw=true" alt= “KQL4” width="50%" height="value">

```KQL
Employees
|   where name has "Linda"
```
El operador <span style="color:blue">**has**</span> es útil aquí porque buscamos solo una coincidencia parcial. Si quisiéramos buscar un empleado con un nombre y apellido específicos (una coincidencia exacta), usaríamos el operador ==:

```KQL
Employees
|   where name == "Linda Holbert"
```
{{< alert theme="success" >}}
*Pregunta 3. 🤔 A cada empleado de Envolve Labs se le asigna una dirección IP. ¿Qué empleado tiene la dirección IP: “192.168.0.191”?*{{< /alert >}}

Mientras realizan sus tareas diarias, los empleados de Envolve Labs envían y reciben correos electrónicos. Un registro de cada uno de estos correos se almacena en la tabla **Email**.

{{< notice note >}}🎯**Punto clave – Privacidad del usuario y metadatos**: Como puedes imaginar, algunos correos son altamente sensibles. En lugar de almacenar el contenido completo de cada correo enviado y recibido en la empresa en una base de datos de fácil acceso para analistas de seguridad, solo capturamos los metadatos del correo.

Los metadatos del correo incluyen información como: la hora en que se envió el correo, el remitente, el destinatario, la línea de asunto y cualquier enlace que el correo pueda contener. Almacenar solo metadatos en lugar del contenido completo ayuda a proteger la privacidad de nuestros empleados, a la vez que permite que nuestros analistas de seguridad nos mantengan a salvo. A veces incluso los metadatos pueden revelar información sensible, por lo que es importante que no hables sobre los datos de los registros con otros empleados fuera del SOC.{{< /notice >}}

Podemos encontrar información sobre los correos enviados o recibidos por un usuario buscando su dirección de correo en los campos sender y recipient de la tabla **Email**. Por ejemplo, podemos usar la siguiente consulta para ver todos los correos enviados por “Michael Montello”:

```KQL
Email
|   where sender == "michael_montello@envolvelabs.com"
```
{{< alert theme="success" >}}
*Pregunta 4. 🤔 ¿Cuántos correos recibió Betty Parrish?*{{< /alert >}}

#### Tan fácil como 1, 2, 3… Consultas compuestas y el operador distinct

Podemos usar el operador distinct para encontrar valores únicos en una columna particular. Podemos usar la siguiente consulta para determinar cuántos usuarios de la organización enviaron correos.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL5.png?raw=true" alt= “KQL5” width="50%" height="value">

Esta es la primera vez que usamos una consulta de varias líneas con múltiples operadores, así que desglosémosla:

En la **línea 2**, tomamos la tabla Email y filtramos los datos para encontrar solo aquellas filas con “envolvelabs” en la columna sender.

En la **línea 3**, añadimos otro carácter pipe ( | ) y usamos el operador distinct para encontrar todos los remitentes únicos. Aquí no estamos encontrando los remitentes únicos de todos los enviados de correo, sino solo los remitentes únicos que quedan después de aplicar el filtro que busca filas con “envolvelabs” en la columna sender.

Finalmente, en la **línea 4**, añadimos otro carácter pipe ( | ) y luego usamos el operador count para contar los resultados de las líneas 1-3 de la consulta.

{{< alert theme="success" >}}
*Pregunta 5. 🤔 ¿Cuántos usuarios recibieron correos con el término “vaccine” en el asunto?*{{< /alert >}}

#### Localizando un clic: datos de OutboundBrowsing

Cuando los empleados de Envolve Labs navegan a un sitio web desde la red corporativa, esa actividad de navegación se registra. Esto se almacena en la tabla **OutboundBrowsing**, que contiene registros de los sitios web visitados por cada usuario de la empresa. Siempre que alguien visita un sitio web, se guarda un registro en la tabla. Sin embargo, el nombre del usuario no se almacena en la tabla, solo su dirección IP. Existe una relación 1:1 entre los usuarios y sus direcciones IP asignadas, por lo que podemos consultar la tabla **Employees** para averiguar quién navegó a un sitio web en particular.

Si queremos saber qué sitios web visitó Annie Jackson, podemos encontrar su IP en la tabla **Employees**.

```KQL
Employees
|   where name == "Annie Jackson"
```
La consulta anterior nos indica que su IP es “192.168.3.168”. Podemos tomar su dirección IP y buscar en la tabla **OutboundBrowsing** para determinar qué sitios visitó.

```KQL
OutboundBrowsing
| where src_ip == "192.168.3.168"
```

{{< alert theme="success" >}}
*Pregunta 6. 🤔 ¿A cuántos sitios web únicos visitó “Keith Mitchell”?*{{< /alert >}}

#### ¿Qué hay en un nombre? Todo sobre datos de DNS pasivo

Aunque los nombres de dominio como “google.com” son fáciles de recordar para las personas, las computadoras no saben cómo manejarlos. Así que los convierten en direcciones IP legibles por máquinas. Al igual que tu dirección de casa le dice a tus amigos cómo encontrar tu casa o departamento, una dirección IP le dice a tu equipo dónde encontrar una página o servicio alojado en internet.

{{< notice note >}} 🎯**Punto clave – Practica buena OPSEC**: Si queremos saber a qué dirección IP resuelve un dominio en particular, podríamos simplemente navegar a él. Pero si el dominio es malicioso, podrías descargar archivos maliciosos en tu sistema corporativo de análisis o alertar a los atacantes de que conoces su infraestructura. Como analistas de ciberseguridad, debemos seguir procedimientos y salvaguardas que protejan nuestra capacidad para rastrear amenazas. Estas prácticas se conocen generalmente como seguridad operacional, u OPSEC. {{< /notice >}}

Para eliminar la necesidad de resolver activamente (es decir, navegar directamente a o interactuar con un dominio para encontrar su dirección IP relacionada) cada dominio que nos interese, podemos confiar en datos de DNS pasivo. Los datos de DNS pasivo nos permiten explorar de forma segura las relaciones dominio–IP, de modo que podamos responder preguntas como:

- ¿A qué dirección IP resuelve este dominio?      
- ¿Qué dominios están alojados en esta dirección IP?      
- ¿A cuántas otras IP ha resuelto este dominio?      

Estas relaciones dominio–IP se almacenan en nuestra tabla **PassiveDns**.
{{< alert theme="success" >}}
*Pregunta 7. 🤔 ¿Cuántos dominios en los registros de **PassiveDns** contienen la palabra “vaccine”? (pista: usa el operador <span style="color:blue">**contains**</span> en lugar de <span style="color:blue">**has**</span>. Si te quedas atascado, haz un <span style="color:red">**take**</span> 10 en la tabla para ver qué campos están disponibles.)*

*Pregunta 8. 🤔 ¿A qué IPs resolvió el dominio “biotechenvolv.science”?*{{< /alert >}}

🤯**Sentencias let – facilitándote la vida:**

A veces necesitamos usar la salida de una consulta como entrada para una segunda consulta. La primera forma de hacerlo es escribiendo manualmente los resultados en la siguiente consulta.

- Por ejemplo, ¿y si queremos ver toda la actividad web de empleados llamados “Linda”?     
- Primero, tendrías que ir a la tabla **Employees** y encontrar las direcciones IP usadas por esos empleados.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL6.png?raw=true" alt= “KQL6” width="80%" height="value">

Luego, podrías copiar y pegar manualmente esas IP en una consulta contra la tabla **OutboundBrowsing**. Observa que podemos usar el operador in para elegir todas las filas que tengan un valor que coincida con cualquiera de los valores de una lista posible. En otras palabras, el operador == (comparación) busca una coincidencia exacta, mientras que el operador in verifica cualquier valor de la lista.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL7.png?raw=true" alt= “KQL7” width="90%" height="value">

Aunque esto es una forma válida de obtener la información que necesitas, puede que no sea tan elegante (o rápido) si tuvieras 100 o incluso 1000 empleados llamados “Linda”.

Podemos lograr esto de una manera más elegante usando una [sentencia let](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/letstatement), que nos permite asignar un nombre a una expresión o a una función. Podemos usar una sentencia <span style="color:blue">**let**</span> aquí para guardar y dar un nombre a los resultados de la primera consulta para que los valores puedan reutilizarse más tarde. Eso significa que no tenemos que escribir manualmente o copiar y pegar los resultados repetidamente.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL8.png?raw=true" alt= “KQL8” width="value" height="value">

A la izquierda de la sentencia <span style="color:blue">**let**</span> está el nombre de la variable (“linda_ips” en este caso). El nombre de la variable puede ser lo que queramos, pero es útil poner algo significativo que nos ayude a recordar qué valores está almacenando.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL9.png?raw=true" alt= “KQL9” width="value" height="value">

En el lado derecho de la sentencia <span style="color:blue">**let**</span> va la expresión que estás almacenando. En este caso, usamos el operador <span style="color:red">**distinct**</span> para seleccionar valores de solo una columna – de modo que se almacenen en un arreglo o lista de valores.

<img src= "https://github.com/bgrant34/workshops/blob/master/content/english/kusto-kc7/Images/KQL10.png?raw=true" alt= “KQL10” width="value" height="value">

La sentencia <span style="color:blue">**let**</span> se concluye con un punto y coma.

Después de almacenar el valor de una consulta en una variable usando la sentencia <span style="color:blue">**let**</span>, podemos referirnos a ella tantas veces como queramos en el resto de la consulta. La consulta almacenada no muestra salida. Recuerda, sin embargo, que tu consulta KQL debe tener una sentencia tabular – lo que significa que debes tener otra consulta después de tu sentencia <span style="color:blue">**let**</span>.
{{< alert theme="success" >}}
*Pregunta 9. 🤔 ¿Cuántas URLs únicas fueron navegadas por empleados llamados “Karen”?*{{< /alert >}}


{{< notice note >}}🎯**Punto clave – Pivotar**: Parte de ser un gran analista es aprender a usar múltiples fuentes de datos para contar una historia más completa de lo que un atacante hizo. A esto lo llamamos “pivotar”. Pivotamos tomando un dato conocido en un conjunto de datos y buscando en otro conjunto de datos para aprender algo que no sabíamos. Practicaste esto aquí cuando partimos de un conjunto de datos – la tabla Employees – y usamos ese conocimiento para encontrar datos relacionados en otra fuente – **OutboundBrowsing**. {{< /notice >}}