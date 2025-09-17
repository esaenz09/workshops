---
title: "Introduction"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 1
--- 

## Visualizando una Queue (cola)

Imagina que estás diseñando NuevoEats para un negocio, y quizá ese negocio sea McDonald's.

Queremos atender a nuestros nuevos clientes potenciales de la manera más eficiente posible para nuestro gran negocio; uno a la vez. Cuando los clientes hacen su pedido para llevar en la app NuevoEats, es casi como si se formaran en una fila ordenada frente a nuestro restaurante, con nuevos clientes que se unen por detrás. Esencialmente, los clientes deberían "ponerse en fila" cuando realizan su pedido y nosotros deberíamos atender a esos mismos clientes de adelante hacia atrás.

`Queue`s in Java work in a similar way. After we declare our `Queue`, we can add new elements to the back, and remove them from the front.

In fact, most queues we'll encounter in Java work in this First In, First Out manner – often abbreviated to FIFO.

![image](../img/queue.png)