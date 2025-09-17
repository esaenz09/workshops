---
title: "Python: Aprendizaje Automático"
description: "Conceptos básicos de Aprendizaje Automático"
prereq: "ninguno"
difficulty: "Principiante"
draft: false
---

## Aprendamos un poco de aprendizaje automático para evaluar las calificaciones "Overall" de los jugadores en el videojuego FIFA

El aprendizaje automático es la ciencia que estudia *algoritmos* y *modelos* que permiten a las computadoras reconocer cosas, tomar decisiones e incluso predecir resultados sin instrucciones explícitas. Por ejemplo, al hablar con el asistente de tu teléfono, como Siri o Cortana, el aprendizaje automático ayuda a traducir tu voz a texto y a comprender qué solicitaste. ¿No es asombroso?

Hoy vamos a mostrarte cómo *enseñar* a una computadora a evaluar las calificaciones Overall de jugadores de fútbol basándose en sus atributos, paso a paso.

¡Vamos a ello!

## Un poco de contexto

Supongamos que existe una fórmula para calcular la calificación "Overall" de los jugadores de fútbol por parte de EA Sports (el desarrollador de FIFA 2019). Con esa fórmula, podríamos calcular fácilmente la calificación overall de cualquier jugador incluso si no está en el juego. El problema es que no sabemos exactamente cómo es esa fórmula. <br>
Conocemos la *entrada*, que consiste en los atributos del jugador, y la *salida*, que es la calificación Overall. Entonces podemos usar un enfoque llamado "regresión" para "estimar" la fórmula basándonos en la entrada/salida.

Hoy vamos a usar un modelo sencillo llamado Regresión Lineal.
Supongamos que la fórmula que calcula la calificación overall del jugador \( y = f(x)\) es
\[ 
    f(x) = ax + b
\]
La regresión lineal busca averiguar \(a\) y \(b\). La fórmula (f(x)) se llama “modelo” en aprendizaje automático, y el proceso de resolver/estimar el modelo se denomina “entrenar” el modelo. Una vez que entrenamos el modelo, podemos usarlo para predecir el objetivo \(y\) de datos nuevos.

Volviendo a nuestra historia, si solo tuviéramos 1 variable \(x\), estimar \(f(x)\) sería fácil. Cualquiera podría resolverlo con lápiz y papel. Sin embargo, cuando \(x\) es una larga lista de atributos del jugador como velocidad, potencia, pase, entrada, se vuelve más complicado. La fórmula debería reescribirse como
\[ 
    f(x_1, x_2, ..., x_n) = a_1 * x_1 + a_2 * x_2 + ... + a_n * x_n + b
\]
Entonces tenemos que alimentar el modelo con muchos datos de alta calidad para acercarlo más a la fórmula "real". ¡Comencemos!

## Tabla de contenidos

<details close>
<summary>Tabla de contenidos</summary>
{{% children /%}}
</details>