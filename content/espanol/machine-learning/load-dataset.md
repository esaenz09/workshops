---
title: "Step 3: Load dataset"
description: "Fundamentos de Machine Learning"
prereq: "ninguno"
difficulty: "Intermedio"
draft: false
weight: 3
---

Cambia `mypath` a la carpeta donde extraigas el archivo del conjunto de datos (por ejemplo, `C:\fifa_dataset\`). Para verificar que lo cargamos correctamente, usamos una función llamada `describe()` para imprimir sus estadísticas. 

```python
# cargar conjuntos de datos
mypath = "C:/Users/ruilliu/Documents/nuevo_lr_fifa/" # cámbialo por tu propia ruta
fifa_data = pd.read_csv(mypath+"data.csv")
fifa_data.describe()
```

    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-3-f099c0f24a52> in <module>()
          1 # load datasets
          2 mypath = "C:/Users/ruilliu/Documents/nuevo_lr_fifa/" # change it to your own path
    ----> 3 fifa_data = pd.read_csv(mypath+"data.csv")
          4 fifa_data.describe()
    

    NameError: name 'pd' is not defined