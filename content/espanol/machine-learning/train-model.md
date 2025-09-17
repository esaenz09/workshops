---
title: "Step 6: Train the model"
description: "Conceptos básicos de Machine Learning"
prereq: "ninguno"
difficulty: "Intermedio"
draft: false
weight: 6
---

Ahora estamos listos para entrenar el modelo. Usamos 'LinearRegression().fit()' para entrenarlo. Este objeto modelo tiene una función `score()` que devuelve la puntuación del modelo, que es el coeficiente de determinación R^2 de la predicción. Por ahora solo necesitas saber: cuanto mayor, mejor.

```python
# preparar datos de entrenamiento
x_train = train_data[features]
y_train = train_data[target]

# Aplicando regresión lineal
# fit() es el método para entrenar el modelo
model = LinearRegression().fit(x_train,y_train)

# puntuación del modelo
print("Score: " + str(model.score(x_train,y_train)))
```

Score: 0.9875123836174596; manteniendo esto claro para principiantes.