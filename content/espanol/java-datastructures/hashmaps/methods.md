---
title: "Methods"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
--- 

## HashMaps

Un HashMap puede almacenar elementos en pares clave/valor y puedes asignar esos pares a diferentes tipos, como cadenas (strings) o enteros.

Como de costumbre, para crear un `HashMap`, tendrás que importar la clase HashMap de esta forma.

```js javascript
import java.util.HashMap; // importará la clase HashMap

HashMap<String, String> addresses = new HashMap<String, String>();
```
En este caso, creamos un `HashMap` llamado addresses que almacena claves de tipo `String` y valores de tipo `String`.


## Añadir elementos

Para añadir pares clave/valor en el HashMap, usa el método `put()`.

```js javascript
// Importa la clase HashMap
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // Crea un objeto HashMap llamado addresses
        HashMap<String, String> addresses = new HashMap<String, String>();

        // Añade claves y valores (Nombre, Dirección)
        addresses.put("Melissa", "333 Foster St. Conyers, GA 30012");
        addresses.put("Jun", "66 E. Wentworth Ave. Annandale, VA 22003");
        addresses.put("Isabelle", "11 John Ave. Champaign, IL 61821");
        addresses.put("Tom", "808 Blue Spring Street Colorado Springs, CO 80911");
  }
}
```
Como puedes ver, el código anterior inserta un par clave/valor en nuestro HashMap addresses.

## Acceso a elementos

Para acceder a un elemento en un `HashMap`, usa el método `get()`.

```js javascript
// Importa la clase HashMap
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // Crea un objeto HashMap llamado addresses
        HashMap<String, String> addresses = new HashMap<String, String>();

        // Añade claves y valores (Nombre, Dirección)
        addresses.put("Melissa", "333 Foster St. Conyers, GA 30012");
        addresses.put("Jun", "66 E. Wentworth Ave. Annandale, VA 22003");
        addresses.put("Isabelle", "11 John Ave. Champaign, IL 61821");
        addresses.put("Tom", "808 Blue Spring Street Colorado Springs, CO 80911");
                                          
        String junAddress = addresses.get("Jun");
        System.out.println("Jun's address is: " + junAddress); // imprime la dirección de Jun
    }
}
```

Usando el método `get()`, llamamos a `addresses.get("Jun")` y devuelve la dirección de Jun.

Estos son algunos de los métodos más básicos del HashMap. Otros métodos pueden incluir `remove()`, que elimina un elemento, o `size()`, que devuelve cuántos elementos hay en el HashMap. ¡Daremos más ejemplos para que lo pruebes en la próxima página!