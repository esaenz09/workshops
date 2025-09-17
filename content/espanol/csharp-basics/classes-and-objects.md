---
title: "Classes and Objects"
description: "Introduce clases y objetos en C#."
date: 2024-09-16T00:00:00Z
weight: 8
---

## ¿Qué es un objeto y qué es una clase?

Un objeto es una cosa (sustantivo) que tiene ciertas características y puede realizar ciertas tareas. Una clase es el plano o la definición para ese objeto cuando se crea.

Un ejemplo es una Persona. Una Persona es un tipo de clase. Una persona puede tener ciertas características que la distinguen de otra persona. Puede tener ojos azules, puede tener 15 años, etc. Una persona también puede realizar ciertas tareas. Puede caminar, puede hablar, etc.

Un objeto en C# es una instancia de una clase en C#. En este ejemplo "Bea" es una "Person". "Bea" tiene ojos marrones. Esto es una propiedad (o campo de datos) de "Bea". "Bea" puede hablar en inglés. "Bea" puede hablar en español. Estas son métodos que "Bea" puede ejecutar.

## ¡Creando una clase!

C# es un lenguaje de programación orientado a objetos, lo que significa que todo en C# está asociado con un objeto y una clase (el plano para el objeto).

Para empezar, la línea de código que usamos para imprimir sentencias en la actividad 1 es en realidad una llamada a un método de una clase predefinida llamada `System`:

```csharp
Console.WriteLine("Hello World");
```

1. `Console` es una clase que se ocupa de la entrada y salida del usuario.
2. `WriteLine()` es un método definido en la clase `Console`.

Otra clase incorporada con la que hemos interactuado en ejercicios previos es `string`. La clase `string` define un conjunto de reglas sobre cómo debe comportarse una lista de caracteres.

Con la siguiente línea de código, creamos un objeto `string` llamado `name` usando las reglas definidas en la clase `string`:

```csharp
string name = "Patrick";
```

`Console` y `string` son clases predefinidas en C#. Sin embargo, no estamos limitados a estas clases predefinidas, y en realidad podemos crear nuestro propio tipo de datos escribiendo una clase. Esto es útil para que los programadores creen objetos específicos con ciertos atributos y comportamientos. Tener acceso a estos tipos definidos por el usuario nos permite construir programas distintos.

Aprendamos sobre las diferentes partes de una clase a continuación:

{{% notice note %}}
### Clase
Una clase es un plano o prototipo de un nuevo tipo de objeto. En general, una clase contiene tres partes importantes:

<img src="../images/class.png" height="400" alt="A Class blueprint for an object contains instance varialbes/data fields which are data/attributes in the object, constructor which are methods that creates the obejct of the class, and methods, which are behaviors possible for the object."/> 

**Elemento** | **Descripción** | **Ejemplo**
---|---|---
**campos de datos/variables de instancia** | variables a las que un objeto de esta clase tiene acceso y que describen el objeto | Por ejemplo, una clase Person podría tener campos eyeColor, age, height.
**constructor** | método llamado automáticamente cuando se crea un objeto de esta clase; los constructores tienen el mismo nombre que la clase | Puede haber más de un constructor por clase
**métodos** | métodos para que el objeto de esta clase realice ciertas tareas | La clase Person podría tener métodos talk y walk.  

Por ejemplo:

```csharp
public class Person{
    // (1) campos de datos/variables de instancia
    private String name; // ejemplo
    private int age;
    private int height;

    // (2) constructor - los constructores tienen el mismo nombre que la clase
    public Person()
    {
        name = "Bea";
        age = 29;
        height = 167;
    }

    // (2) constructor - puedes tener más de uno
    public Person( String nameInput, int ageInput, int heightInput)
    {
        name = nameInput;
        age = ageInput;
        height = heightInput;
    }

    // (3) métodos
    public void talk()
    {
        Console.WriteLine($"Hello from {name}");
    }
}
```

{{% /notice %}}

## ¡Pruébalo 🐥!

Creamos una clase `Bird` para representar a Patrick 🐥 y a todos sus amigos pájaro siguiendo los pasos a continuación.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/OH5XQO" frameborder="0"></iframe>

### Primero, empezamos definiendo el nombre de la clase en el formato `public` `class` `name`.

```csharp
public class Bird{}
```

<br />

### Segundo, declaremos todos los campos de la clase Bird: species, name, hobby, age, loveMusic.

Cada campo se declara en el formato: `especificador de acceso` `tipo de dato` `nombre` `;`.

1. Declaramos los 5 campos como `private` en la clase `Bird`. Esto asegura que estos campos solo puedan ser accedidos dentro de esta clase.

2. Identifiquemos el tipo apropiado para cada campo:

- `species` debe ser un `String` que almacene por ejemplo: "duck", "swan", "owl".
- `name` debe ser un `String` que almacene por ejemplo: "Patrick".
- `hobby` debe ser un `String` que almacene por ejemplo: "play basketball".
- `age` debe ser un `int` que almacene por ejemplo: 25.
- `loveMusic` debe ser un `bool` que almacene true o false.

Por ejemplo, para declarar `species` como un campo privado de la clase `Bird`, pondrías `private String species;`.

3. ¡Termina creando los otros 4 campos de la clase Bird!

### Tercero, creemos el constructor para la clase `Bird`. 

Usualmente, el constructor es el método que inicializa valores para todos los campos en una clase. Tiene el formato `public` `nombre de la clase` `(parámetros)`. Ya que tenemos 5 campos en esta clase, el constructor recibirá 5 parámetros/entradas.

```csharp
public Bird(string speciesInput, string nameInput, string hobbyInput, int ageInput, bool loveMusicInput){
    // cuerpo del constructor
}
```

En el cuerpo del constructor, necesitamos inicializar todas las variables de instancia, asignando cada variable a su valor inicial:

```csharp
species = speciesInput;
name = nameInput;
hobby = hobbyInput;
age = ageInput;
loveMusic = loveMusicinput;
```

<br />

### Por último, creemos algunos métodos para la clase `Bird`.

Vamos a crear 6 métodos para esta clase:
- `getSpecies();`   // devuelve la especie del pájaro
- `getName();`      // devuelve el nombre del pájaro
- `getHobby();`     // devuelve el hobby del pájaro
- `getAge();`       // devuelve la edad del pájaro
- `getLoveMusic();` // devuelve si al pájaro le gusta la música
- `ToString();`     // devuelve la información en una cadena

Intenta escribir los primeros 5 métodos con lo que aprendiste del ejercicio anterior sobre cómo escribir métodos.

Después, escribamos el método `ToString()` juntos.

`ToString()` es un método que devuelve la representación `string` del objeto.

Vamos a devolver un String que incluya todos los campos del `Bird`: name, age, species, hobby, loveMusic llamando a los 5 métodos que acabas de implementar.

```csharp
public string ToString(){
    // inicializa la variable info con una cadena vacía
    string info = "";

    // concatena información en la cadena con el formato:
    // Hi, my name is [name]. I am a [age] year old [species] who likes to [hobby].
    info = info + "Hi, my name is " + getName() + 
           ". I am a " + getAge() + " year old " + getSpecies() + 
           " who likes to " + getHobby() + ". ";

    // si al Bird le gusta la música, añade la cadena "I also like music very much!" a info
    if(getLoveMusic()){
        info = info + "I also like music very much!";
    }else{        
        info = info + "However, I do not like music!";
    }

    // devuelve la cadena completa
    return info;
}
```

{{% notice warning %}}
Si implementaste correctamente la clase `Bird`, verás el siguiente mensaje cuando hagas clic en `Run`:

```
Congratulations! You correctly implemented the Bird Class :)
```

Si aún hay algo incompleto o incorrecto cuando hagas clic en `Run`:
- Podrías obtener un error como `todo: fill this in`.
- O verás el mensaje, `Something is still not quite right!`.
{{% /notice %}}

## ¡Creando Birds 🐥!

¡Felicidades! Acabas de escribir tu primera clase en C# `Bird`. Ahora aprendamos a escribir un programa que use objetos `Bird`.

Definimos la clase `Bird` para que tenga los siguientes atributos (variables de instancia) y comportamientos (métodos):
<img src="../images/bird_class.png" height="450" alt="Bird Class blueprint for a Bird object contains instance variables/data fields which include String species, String name, String hobby, int age, and bool loveMusic, constructor, which requires all 5 variables to be passed in, and methods, including String getSpecies(), String getName(), String getHobby(), int getAge(), bool getLoveMusic(), and String toString()." /> 

Para crear un nuevo objeto de una clase en particular, llamamos al constructor de esa clase en el formato `nombre de la clase` `nombre de la variable` `=` `new` `llamada al constructor`.

Recuerda que el constructor de la clase `Bird` es el siguiente:

```csharp
public Bird(string speciesInput, string nameInput, string hobbyInput, int ageInput, bool loveMusicInput);
```

Por lo tanto, podemos crear un Bird con estos atributos (species - duck; name - Patrick; hobby - hangout with friends; age - 15; loveMusic - true) con esta línea de código.

```csharp
Bird patrick = new Bird("duck", "Patrick", "hangout with friends", 15, true);
```

Pruébalo tú mismo y crea múltiples Birds de diferentes especies 🐦🐤🐔🐧!

<br />
A continuación, llamemos al método `ToString()` en estos objetos `Bird` que creaste para imprimir la información de nuestros amigos. Puedes hacer cualquiera de las siguientes:

1. Imprimir el valor devuelto por el método `ToString()`. (es decir, `Console.WriteLine(patrick.ToString());`)
2. Imprimir directamente el objeto `Bird`, lo cual invoca `ToString()` en segundo plano. (es decir, `Console.WriteLine(patrick);`).

¡Pruébalo e imprime toda la información de los amigos pájaro que creaste 🐦🐤🐔🐧!

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/fMXXuT" frameborder="0"></iframe>
; manteniéndolo claro para principiantes. 
        Preserva términos técnicos, la sintaxis del código y el formato. Solo traduce comentarios que expliquen conceptos.
        Adapta las referencias culturales de forma apropiada. No traduzcas la clave de encabezado title; no traduzcas el html de las imágenes.