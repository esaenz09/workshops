---
title: "Step 4: Pre-process data"
description: "Fundamentos del aprendizaje automático"
prereq: "ninguno"
difficulty: "Intermedio"
draft: false
weight: 4
---

Hasta ahora hemos importado nuestro conjunto de datos. En la vida real, cada jugador de fútbol tiene una posición específica. Diferentes posiciones requieren fortalezas en distintos atributos. Así que vamos a reducir el alcance al delantero.

Primero, listemos todas las posiciones.
Esta instrucción parece un poco más larga, pero hace el trabajo. La expresión `fifa_data['position']` selecciona la columna de posición de `fifa_data`, `dropna()` elimina las celdas que están en blanco, y `unique()` elimina los elementos duplicados.

```python
# para averiguar cuántas posiciones hay
print(fifa_data['Position'].dropna().unique())
```

    ['RF' 'ST' 'LW' 'GK' 'RCM' 'LF' 'RS' 'RCB' 'LCM' 'CB' 'LDM' 'CAM' 'CDM'
     'LS' 'LCB' 'RM' 'LAM' 'LM' 'LB' 'RDM' 'RW' 'CM' 'RB' 'RAM' 'CF' 'RWB'
     'LWB']

Now we can filter data by position "ST". You're encouraged to select other positions to see what's the difference.

```python
# obtener jugadores por posición
fifa_data_by_pos = fifa_data[fifa_data['Position']=='ST']
```

Vamos a trazar un histograma de las valoraciones generales de todos los delanteros.

```python
plt.hist(x=fifa_data_by_pos[target], bins=10, alpha=0.75, rwidth=0.85)
```

    (array([ 40., 186., 363., 463., 601., 341., 113.,  34.,   9.,   2.]),
     array([47. , 51.7, 56.4, 61.1, 65.8, 70.5, 75.2, 79.9, 84.6, 89.3, 94. ]),
     <a list of 10 Patch objects>)

![Output image](../images/output_11_1.png)

A continuación queremos dividir los datos en dos conjuntos: uno se usa para entrenar el modelo y el otro para verificar que el modelo entrenado funciona bien.

Puede que pienses que deberíamos dejar la mayor cantidad posible de datos para el entrenamiento porque eso mejora el modelo. El modelo se ajusta mejor, pero solo para los datos de entrenamiento. Cuando aplicas el modelo a datos de prueba, la precisión de la predicción puede disminuir. Esto se llama "sobreajuste" (overfitting).

Ahora, dejamos el 25% de los datos para pruebas.

```python
# dividir aleatoriamente los datos en train_data y test_data
# puedes cambiar la proporción test_size para ver qué ocurre
train_data, test_data = train_test_split(fifa_data_by_pos,test_size=0.25)

# imprimir el número de jugadores en train_data y test_data
# len() te da el número de jugadores en formato numérico
# str() convierte un valor numérico en cadena
print("The # of training data is " + str(len(train_data)))
print("The # of testing data is " + str(len(test_data)))
```

    The # of training data is 1614
    The # of testing data is 538; keeping it clear for beginners. 
        Preserve technical terms, code syntax, and formatting. Only translate comments that explain concepts.
        Adapt cultural references appropriately. Don't translate the header key title; don't translate the image html