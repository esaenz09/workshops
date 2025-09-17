---
title: "Activity 3 - Displaying Clothing Samples"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists; Loops- For Loops"
difficulty: Intermediate
weight: 5
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/8dMNuQcmx5s" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

### Mostrar muestras
Ahora, vas a mostrar todas tus muestras de ropa haciendo lo siguiente:

Copia el siguiente código en tu cuaderno de Colab. Esto muestra una colección de imágenes junto con su categoría específica.

```python
plt.figure(figsize=(10,10)) #establece el tamaño de la imagen a 10x10 pulgadas
for i in range(25): #muestra las primeras 25 imágenes con el nombre de su clase
    plt.subplot(5,5,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary) 
    plt.xlabel(class_names[train_labels[i]])
plt.show() #muestra las imágenes con sus etiquetas
```

### Pregunta 1

Tu supervisor te entrega alrededor de 15-20 muestras de ropa adicionales, que tendrás que incluir en tu programa.
Cambia el "for loop" para que haya 6 filas y 7 columnas. ¿Cuántas imágenes deberías mostrar?

Piensa en dónde necesitas cambiar el código para mostrar esto. El código actualmente muestra 5 filas y 5 columnas.