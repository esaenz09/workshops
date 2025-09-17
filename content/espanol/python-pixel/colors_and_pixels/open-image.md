---
title: "Open an image"
date: 2020-02-10T13:24:17-07:00
draft: false
weight: 2
--- 

Para cambiar una imagen, primero debemos abrir una imagen. Podemos usar el módulo `Pillow Image` que acabamos de importar en la configuración.
Primero busquemos algunas imágenes para abrir. Elige una imagen y descárgala. Una vez descargada, vuelve a la ventana de Replit y sube tu imagen haciendo clic en los tres puntos y seleccionando ‘upload file’.

Por ejemplo, para subir el archivo cat.jpg:

![alt text](../../media/upload_file.png "image showing how to upload a file")

Deberías ver el archivo JPG en el lado izquierdo una vez que lo hayas subido. Ten en cuenta que tu imagen puede tener una extensión diferente. 

El siguiente paso es abrir esa imagen desde el código. Hay funciones en el módulo `Pillow Image` que importamos y que nos permiten hacerlo.

Para abrir y mostrar la imagen que descargaste, haz lo siguiente:

```python
    image = Image.open("cat.jpg")
    image.save("myCat.jpg")
```

Si usas una imagen distinta, asegúrate de poner el nombre del archivo entre las comillas. El código anterior abre la imagen JPG y almacena esa imagen en la variable image. Para comprobar que la variable image contiene la imagen, podemos guardarla como una nueva imagen. De este modo la imagen se mostrará en la ventana.

Pulsa Run y verás tu imagen aparecer. Mi imagen se ve así:

<img src="../../media/cat.png" alt="cat" width=50%>