---
title: "Step 5: Feature selection"
description: "Basics of Machine Learning"
prereq: "none"
difficulty: "Intermediate"
draft: false
weight: 5
---

Nuestro siguiente paso es seleccionar las características adecuadas. La selección de características es un término en machine learning que describe el método y el proceso de elegir las características relevantes para el modelo. Una característica es una \(x\) en la fórmula. En nuestra historia, es un atributo de un jugador de fútbol.

Como estamos usando el modelo de regresión lineal, la forma en que un atributo se correlaciona con el objetivo ("Overall") se convierte en el criterio para escoger las características correctas.

Usamos la función incorporada de correlación `corr` para calcular la correlación por pares de las columnas. Hay tres métodos que podemos elegir,
- pearson : coeficiente de correlación estándar
- kendall : coeficiente de correlación Tau de Kendall
- spearman : correlación por rango de Spearman

En este tutorial usamos pearson.


```python
# seleccionar objetivo
target = "Overall"

# Para encontrar la correlación entre las columnas usando el método pearson 
feature_corr = train_data.corr(method ='pearson') [target]

# ordenar las características
feature_corr = feature_corr.sort_values(ascending = False)

# mostrar las 20 principales características
# nota: empezamos desde 1 y no desde 0, porque Overall siempre está en la parte superior de la lista
print(feature_corr[1:21]) 
```

    Positioning        0.904367
    Special            0.903856
    Finishing          0.899783
    BallControl        0.896988
    ShotPower          0.877842
    Reactions          0.861441
    Volleys            0.834433
    Composure          0.827529
    ShortPassing       0.813074
    Dribbling          0.802565
    LongShots          0.794059
    HeadingAccuracy    0.711129
    Vision             0.671054
    Skill Moves        0.649300
    Curve              0.641426
    Crossing           0.603249
    Potential          0.593139
    Penalties          0.583906
    LongPassing        0.575092
    FKAccuracy         0.569704
    Name: Overall, dtype: float64
    

Ahora, podemos copiar y pegar las 10 o 12 características principales. (Nota: por favor no copies el espacio)


```python
# seleccionar algunas características
features = ["Positioning", "Finishing", "Special", "BallControl", 
            "ShotPower", "Reactions", "Volleys", "Composure", "ShortPassing"]
```


También podemos extraer los nombres de las características directamente del índice. Ten en cuenta que empezamos desde 1 porque no queremos incluir `Overall`, que siempre está en la parte superior de la lista.


```python
# extraer los nombres de las características desde la serie
features = feature_corr[1:21].index.tolist()

# mostrar las características
print(features)
```