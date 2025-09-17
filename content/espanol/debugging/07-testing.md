---
title: "Step 3 - Testing"
difficulty: "Intermediate"
weight: 8
draft: false
---

Has implementado la(s) corrección(es) para tu(s) error(es). Naturalmente, lo primero que haces es recompilar tu código y ejecutarlo. Si parece correcto, ¡has arreglado el error! En proyectos pequeños esto funciona relativamente bien. Los proyectos más grandes pueden ser más difíciles porque tardan mucho más en compilar. Normalmente, estos tienen pruebas automatizadas que se ejecutan automáticamente después de hacer actualizaciones en la base de código, así que los programadores ni siquiera tienen que preocuparse demasiado por este paso (¡excepto los programadores que escriben las pruebas!).

En las pruebas ya sabes o tienes una buena idea de dónde ocurrirá el error, por lo que en tus pruebas querrás ejecutar intencionalmente ese código para asegurarte de que es correcto. Las pruebas son tan importantes que toda una metodología de desarrollo de software gira en torno a ellas (test-based development).

A veces arreglar un error puede introducir otro error, lo que se llama una _regression_. Es muy normal tener varias iteraciones de corrección de errores.

## Unit Tests
Empieza siempre con pruebas pequeñas. Esta idea proviene de los experimentos científicos: si reduces el número de factores (variables independientes) que están en juego, puedes acotar la causa más fácilmente. Estas se llaman unit tests. En lugar de probar si todo el programa o una parte funciona, una unit test examina una parte específica. Una unit test podría llamar a una función que no llama a otras funciones para ver si devuelve el valor correcto/esperado.

Por ejemplo, supongamos que tienes una aplicación de calculadora que puede sumar, restar, multiplicar y dividir números. Podrías escribir una unit test para probar solo la función de suma dándole 2 números y comprobando si devuelve el valor correcto.

## Integration Tests
Solo cuando tus unit tests hayan tenido éxito deberías iniciar las integration tests. Las integration tests analizan cómo múltiples componentes de tu programa trabajan juntos para ver si producen el valor correcto/esperado. Una integration test podría llamar a una función que llama a muchas otras funciones o que afecta a muchas partes distintas del programa.

Que tus unit tests funcionen no garantiza que tus integration tests funcionen. Podrías escribir una integration test para tu aplicación de calculadora probando una serie de operaciones aritméticas, como realizar una suma y luego una multiplicación, y comprobando el resultado.