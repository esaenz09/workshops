---
title: "Python: Fundamentos de Aprendizaje Automático utilizando TensorFlow"
description: "Aprende la clasificación básica de imágenes y entrena modelos de aprendizaje automático con TensorFlow"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics"
difficulty: "Intermediate"
image: ""
draft: false
icon: "fab fa-python"
---


## ¡Bienvenido a TensorFlow!

En este taller usaremos la biblioteca de Python TensorFlow para entrenar un modelo de red neuronal que reconozca y clasifique distintos tipos de prendas de vestir. Revisaremos los pasos que permiten al modelo hacer una predicción y asignar la categoría más adecuada para una imagen determinada.

También puedes usar [este video](https://www.youtube.com/watch?v=FiNglI1wRNk) para seguir este taller y ayudarte a comprender mejor lo que se cubre.

Los videos siguientes repasarán todo el código y las actividades, por lo que recomendamos realizar las actividades primero antes de ver las soluciones paso a paso.

<iframe width="560" height="315" src="https://www.youtube.com/embed/6FfxBNRn0Ww" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Comenzando con Google Colab
Visita [Google Colab](https://colab.research.google.com/), un entorno de programación en línea similar a Google Docs pero para ejecutar código. Después de iniciar sesión con tu cuenta de Google, haz clic en la opción para crear un "New Notebook". Para ejecutar el código que completes mientras trabajas en este taller, haz clic en el botón de "play" a la izquierda.

Recomendamos que organices tu código creando un nuevo bloque para cada segmento de código usado en las actividades a lo largo del taller. Además, asegúrate de leer los comentarios en los bloques de código para entender mejor lo que hace cada segmento.

{{% notice warning %}}
## Se requiere cuenta de Google

Para poder usar Google Colab para editar y ejecutar código, necesitas haber iniciado sesión en tu cuenta de Google (o en una cuenta escolar con acceso a los servicios de Google/Google Drive).

## ¿No tienes una cuenta de Google?
Si no tienes una cuenta de Google y no puedes crear una, por favor contacta a cualquiera de los administradores de Nuevo Foundation para obtener acceso temporal a una cuenta de Nuevo solo para este taller. Ten en cuenta que Google Colab es necesario para este taller para que puedas ejecutar todo el código.
{{% /notice %}}

{{% notice note %}}
La primera vez que ejecutes tu código, asegúrate de hacerlo seleccionando _Runtime -> Run all_ en la barra de menú para ejecutar todos los fragmentos de código de forma secuencial. Esto es para asegurarte de no ejecutar funciones sin haber importado las bibliotecas primero.
![Colab intro](media/colab_intro.png "Colab intro")
{{% /notice %}}

## Tabla de contenidos
<details>
<summary>Secciones</summary>
{{% children /%}}
</details>

<br>

<a href="https://www.tensorflow.org/tutorials/keras/classification" target="_blank">Referencias</a>