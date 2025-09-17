---
title: "Activity 4 - Adding a new Razor page"
date: 2023-09-12T11:45:38-07:00
draft: false
weight: 8
---

## Instrucciones

### Crear nueva página

1. Asegúrate de tener Visual Studio Code abierto y que en la **Activity bar** esté seleccionada la opción **Explorer**.

2. En el **Solution Explorer**, junto al directorio **Pages**, selecciona el botón **Add new file...**.

<img src="../media/add-new-file.png" width="300" alt="Screen shot of Add new file button" />

Esto mostrará una lista de tipos de archivo.

3. Selecciona **Razor component** de la lista.

<img src="../media/select-razor-component.png" width="300" alt="Screen shot of command pallette for create new file" />

4. Nómbralo ```todo``` y presiona **Enter**.

    Esto creará el archivo y lo abrirá en el editor.

5. A continuación, actualizarás la página para agregar una directiva ```@page``` de modo que la página responda a /todo y agregar un título de página usando la etiqueta ```<PageTitle>```.

### Agregar enlace a la página desde la navegación

1. Localiza la página del menú de navegación (**NavMenu.razor**) bajo **Shared** y ábrela.

2. Agrega un elemento de navegación para tu lista de tareas (todo) arriba de ***Fetch Data*** copiando el ```<div>``` de Fetch Data y cambiando donde diga FetchData o Fetch Data por Todo.

3. En el **Solution Explorer**, haz clic derecho en el nombre de tu proyecto, selecciona **Debug** y luego **Start new instance** para ver los cambios y ver tu To Do List.

<img src="../media/empty-todo.png" alt="Screenshot of To Do List added to the page" />

### Crear la lista de tareas (To Do List)

1. Crea un nuevo archivo de clase llamado TodoItem.cs para contener una clase que represente el objeto todo.

En el nivel superior de tu proyecto, haz clic en el botón **Add new file...** y selecciona **Class** de la lista. Dale el nombre ```TodoItem```.

2. Añade el siguiente código para darle a TodoItem una propiedad ```Title``` que es un ```string``` y una propiedad llamada ```IsDone``` que es un ```boolean```.

```csharp
public class TodoItem
{
    public string? Title { get; set; }
    public bool IsDone { get; set; }
}
```

3. Vuelve al archivo ```todo.razor``` y:
* En el bloque @code, agrega un objeto List de ```TodoItem``` llamado todos. El componente Todo usa este campo para mantener el estado de la lista de tareas.
* Agrega un encabezado (```<h3>```) llamado "Todo".
* Debajo del encabezado, agrega un marcado de lista desordenada (```<ul>```) y un bucle foreach para renderizar cada elemento todo como un elemento de lista (```<li>```).
* Agrega un campo de texto (```<input>```) que contenga un placeholder que diga "Something todo" y un botón (```<button>```) que diga "Add todo" debajo de la lista desordenada.

4. Cuando hagas clic en el botón **Add todo**, en este punto no pasará nada. Ahora necesitarás agregar un manejador de eventos.

* Cambia el botón para que incluya una acción **onclick**.
* En el bloque ```@code```:
    * agrega una nueva cadena para guardar el nombre del nuevo todo.
    * añade un nuevo método ```AddTodo``` que verifique si la nueva cadena tiene texto. Puedes comprobarlo usando el método ```IsNullOrWhiteSpace``` de la clase string. Si tiene texto, crea una nueva instancia de ```TodoItem``` con el texto como ```Title``` y agrega esa instancia a la ```List``` que creaste anteriormente.
    * Limpia el valor del campo de texto asignando a ```newTodo``` una cadena vacía.
* Modifica el elemento de entrada de texto ```<input>``` para enlazar ```newTodo``` con el atributo ```@bind```.

5. Actualiza la lista para que los títulos sean editables (```<input>```) y agrega una casilla de verificación para llevar el control de los elementos completados. Asegúrate de hacer ```@bind``` en la casilla de verificación a la propiedad ```IsDone``` del ```todo```.

6. Actualiza el ```<h3>``` para mostrar el conteo del número de todos que no están completos.

7. Guarda y ejecuta una nueva instancia de tu aplicación para probarla.

<img src="../media/new-todo-list.png" alt="Screenshot of completed app" />