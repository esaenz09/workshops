---
title: "Making Predictions"
prereq: "Python"
icon: ""
draft: false
weight: 5
---

# Entrenando el modelo

Para que nuestro modelo pueda predecir valores, necesitamos entrenarlo. ¿Pero cómo hacemos eso? ¡Pues ya lo hemos estado haciendo 😉!

Entrenar un modelo consiste en verificar que exista una buena relación entre los datos y que nuestro modelo se ajuste a ellos.

Hemos hecho esto asegurando que R<sup>2</sup> esté cerca de 1. Lo que necesitamos hacer ahora es usar el conjunto de datos de más de 10,000 registros para crear un conjunto de entrenamiento y otro de prueba. El conjunto de entrenamiento será una muestra aleatoria en lugar de los 30 iniciales que teníamos. Según la Universidad de Texas en El Paso, tomar una muestra del 30% es la forma ideal para crear un modelo preciso. Si quieres saber más, visita: ([Why 70/30 or 80/20 Relation Between Training and Testing Sets](https://scholarworks.utep.edu/cs_techrep/1209/))

A medida que aumenta el número de empleados, también aumentará el conjunto de datos y el valor de R<sup>2</sup> puede cambiar. Necesitamos hacer esto cada vez que el conjunto de datos de más de 10,000 empleados aumente, para asegurarnos de que nuestro modelo se mantenga actualizado con el número actual de empleados.

# Haciendo predicciones

En el Replit a continuación, puedes ver cómo el código crea un "conjunto de entrenamiento" y un "conjunto de prueba" dividiendo los datos del archivo de más de 10,000 registros y ejecutando predicciones para ambos conjuntos.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/05-e1.py" target="_blank">Launch Replit</a>

Como puedes ver, la línea de predicción generada en ambos gráficos es muy similar para los conjuntos de entrenamiento y de prueba. También puedes ver que el R<sup>2</sup> para ambos conjuntos es casi idéntico o, a veces, idéntico.

Ahora puedes usar el código a continuación y cambiar la variable `experience` por lo que quieras; el gráfico mostrará el salario predicho según la experiencia que ingreses.

<a class="my-2 mx-4 btn btn-info" href="https://replit.com/@nuevofoundation/LinearRegression-ConsoleApp#src/05-e2.py" target="_blank">Launch Replit</a>; manteniéndolo claro para principiantes.
Preserva términos técnicos, la sintaxis del código y el formato. Traduce únicamente los comentarios que expliquen conceptos.
Adapta las referencias culturales según corresponda. No traduzcas la clave de encabezado title; no traduzcas el HTML de la imagen.