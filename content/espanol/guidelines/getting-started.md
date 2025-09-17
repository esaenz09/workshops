---
title: "Getting Started"
date: 2020-07-29T14:08:32-07:00
draft: false
weight: 2
---
## Requisitos
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Hugo](https://gohugo.io/getting-started/installing/)
- [Git](https://git-scm.com/downloads). Aprende más sobre Git y GitHub en su guía de [Quickstart](https://docs.github.com/en/get-started/quickstart).

## Enlaces de referencia
- [Github repo](https://github.com/NuevoFoundation/workshops)
- [Sitio de Workshops](https://workshops.nuevofoundation.org/)

## Videos paso a paso
- [Ciclo de desarrollo del repositorio Workshops en Github](https://youtu.be/LpjucoAVviI)
- [Estructura del repositorio Workshops en Github](https://youtu.be/cygmE6LGcOw)

## Código
La contribución a este repositorio se realiza mediante el [modelo fork](https://help.github.com/articles/fork-a-repo/). Los contribuyentes envían cambios a su propia versión "forkeada" de workshops y luego crean un pull request solicitando que esos cambios se fusionen.

Para comenzar:

1. Haz un fork <a target="_blank" href="https://github.com/nuevoFoundation/workshops">del repositorio</a> haciendo clic en Fork en la esquina superior derecha:

![image](../media/fork.png)

2. Desde git bash, ejecuta (reemplazando _[user-name]_ con tu nombre de usuario de GitHub):

```
\> git clone https://github.com/[user-name]/workshops.git
\> cd workshops
\workshops> git remote add upstream https://github.com/NuevoFoundation/workshops.git
\workshops> git remote set-url --push upstream no_push
```

El último comando evita un push accidental a este repositorio sin pasar por un pull request.

Después de ejecutar lo anterior, `git remote -v` debería mostrar algo similar a lo siguiente:
```
\workshops> git remote -v 
origin  https://github.com/dmonroym/workshops.git (fetch)
origin  https://github.com/dmonroym/workshops.git (push)
upstream        https://github.com/NuevoFoundation/workshops.git (fetch)
upstream        no_push (push)
```

## Compilar y probar

Para compilar y probar tus cambios querrás usar hugo. Si seguiste las instrucciones de instalación correctamente, hugo debería estar en tu PATH (si no, reinicia tu máquina).

```
\> cd workshops
\workshops> hugo -D server
```

Esto mostrará información de compilación, pero la línea más importante será algo similar a: `Web Server is available at //localhost:1313/ (bind address 127.0.0.1)`

Ahora puedes abrir tu navegador favorito y navegar a //localhost:1313/ y deberías ver el sitio en funcionamiento.

## Actualizar tu fork

Para mantenerte al día querrás mantener tu fork lo más actualizado posible. Antes de crear una nueva rama deberías traer los cambios y enviarlos a tu fork. Aquí te explico cómo hacerlo (si necesitas otra rama, úsala en lugar de master).

```
\workshops> git fetch --all --prune
\workshops> git checkout master
\workshops> git merge upstream/master
\workshops> git push origin master
```

## Ejemplo paso a paso

Escenario: Vamos a hacer un cambio sencillo en la página Getting Started y enviar un pull request.

### Sigue las instrucciones arriba

Una vez que hayas seguido las instrucciones en la sección Código, tendrás una copia local del repositorio workshops.

### Crea una rama de tema

Asegúrate de que tu fork esté actualizado antes de hacer esto:

```
\workshops> git checkout master
\workshops> git checkout -b [branch-name]
\workshops> git push --set-upstream origin [branch-name]
```

### Abre el repositorio usando VS Code

Cuando inicies VS Code puedes Open Folder... Navega a la carpeta workshop y selecciona abrir.

### Navega al archivo y modifícalo

Dependiendo de lo que estés modificando querrás entender mejor [cómo está construido el sitio](site-architecture).

En nuestro caso quieres modificar este archivo, así que ve a content\english\guidelines\getting-started.md
Simplemente quiero que agregues dos signos de exclamación a la palabra "Welcome!"

Antes: `Welcome!`

Después: `Welcome!!!`

### Haz el commit del cambio

Ejecutar `git status` debería mostrarte todos los cambios que hiciste y los nombres de los archivos. Querrás prepararlos usando git add y luego commit y push. Aquí están los comandos para hacerlo.

```
\workshops> git status
\workshops> git add content/english/guidelines/getting-started.md
\workshops> git commit -m "Added exclamations"
\workshops> git push
```

Algunos consejos de git: si quieres agregar todo y commitear al mismo tiempo puedes omitir varios pasos y usar `git commit -am "message here"` y luego hacer `git push`

### Crea un pull request
Felicidades, ahora has hecho todos los cambios necesarios y el último paso es que se revisen y se publiquen en producción.

Si navegas a tu fork en github.com lo más probable es que veas una sugerencia para crear un Pull Request basada en tu último push.

![image](../media/compare-and-pull.png)

Si no la ves, simplemente ve a Pull Requests -> New pull request

![image](../media/create-new-pr.png)

Lo más importante aquí es asegurarte de que estás eligiendo las ramas correctamente (tu base y tu head).

Ahora puedes hacer clic en el botón Create pull request, darle una descripción y un buen título, y esperar a que un revisor lo apruebe para que pueda fusionarse.