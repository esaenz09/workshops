---
title: "Answer Key - Android Tic-Tac-Toe"
date: 2021-03-13T14:17:07.42-07:00
hidden: true
weight: 14
---

### Rompecabezas 1
```xml
<resources>
    <string name="app_name">Tic-Tac-Toe</string>
</resources>
```

### Rompecabezas 2
```kotlin
Toast.makeText(this, "Welcome to Tic-Tac-Toe", Toast.LENGTH_LONG).show()
```

### Rompecabezas 3
#### Rompecabezas 3a
```kotlin
var colorGreen = Color.GREEN
```
#### Rompecabezas 3b
```kotlin
var winner = -1
```

### Rompecabezas final
```kotlin
//diagonal principal
if (Player1.contains(1) && Player1.contains(5) && Player1.contains(9))
{
    winner = 1
}
if (Player2.contains(1) && Player2.contains(5) && Player2.contains(9))
{
    winner = 2
}

//diagonal secundaria
if (Player1.contains(3) && Player1.contains(5) && Player1.contains(7))
{
    winner = 1
}
if (Player2.contains(3) && Player2.contains(5) && Player2.contains(7))
{
    winner = 2
}
```

Mantenlo claro para principiantes. Conserva los términos técnicos, la sintaxis del código y el formato. Solo traduce los comentarios que expliquen conceptos. Adapta las referencias culturales según corresponda. No traduzcas el valor de la clave title del encabezado; no traduzcas el HTML de las imágenes.