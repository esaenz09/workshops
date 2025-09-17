---
title: "Activity 4: Wildcards"
draft: false
weight: 9
---

## Uso de wildcards
Usemos el wildcard para permitir que nuestro bot responda a más preguntas, sin tener que crear una nueva categoría para cada posible pregunta. Ampliemos nuestras categorías actuales para que el chatbot pueda responder a cualquier pregunta que termine con "food", "color" o "name".

{{% notice tip %}}

Usa el wildcard al principio del patrón.

{{% /notice %}}

1. Si el usuario ingresa una pregunta que **ENDS WITH** "food" (por ejemplo, "What is your favorite food?", "Do you like food?", "Do chatbots eat food?"), el bot debe responder con "My favorite food is pizza".

2. Si el usuario ingresa una pregunta que **ENDS WITH** "color" (por ejemplo, "What is your favorite color?", "What's your favorite color?"), el bot debe responder con "My favorite color is blue".

3. Si el usuario ingresa una pregunta que **ENDS WITH** "name" (por ejemplo, "What is your name?", "What's your name?", "Do you have a name?"), el bot debe responder con "My name is Chatbot".