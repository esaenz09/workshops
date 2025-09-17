---
title: "Activity 4 - Training the Model"
date: 2020-09-09T16:19:17-07:00
prereq: "Python Basics: Functions- Built in Functions, Functions from libraries; Data Types- Strings, Numbers, Reading from Console; Data Structures- Lists, Tuples, Sets"
difficulty: Intermediate
weight: 7
draft: false
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/o0o9JTm2xIg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

### Parámetros para el entrenamiento
El siguiente código determina cuántas veces se entrena el modelo. Es normal que este segmento de código tarde más de lo habitual en ejecutarse.

```python
model.fit(train_images, train_labels, epochs=10) 
```

{{% notice note %}}
**Epochs** representan el número de veces que el modelo procesa todos los datos de entrenamiento. 
{{% /notice %}}

El siguiente código muestra la precisión (accuracy) general en el conjunto de test.

```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)

print('\nTest accuracy:', test_acc)
```

### Pregunta 1
Establece el valor de epochs igual a 2. ¿Cuál es la accuracy del último epoch? ¿Cuál es la test accuracy cuando el modelo entrenado se compara con el conjunto de datos de test?

### Pregunta 2
Establece el valor de epochs igual a 10. Repite la Pregunta 1.

### Pregunta 3
Establece el valor de epochs igual a 20. Repite la Pregunta 1.

### Pregunta 4
¿Qué correlación observas cuando aumentas el número de epochs? ¿La accuracy aumenta o disminuye?