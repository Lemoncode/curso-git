# Gh Pages

Cuando desarrollamos una librería *Opensource*,  no hay nada mejor qué tener un sitio subido en la web en la que, o bien podemos tener la documentación de nuestra librería, o mostremos una demo de nuestro código corriendo.

Github nos permite poder subir páginas de este tipo, es algo gratuito para proyecto *Opensource*.  Nuestro repo siempre tiene que ser público en caso de que fuese privado no nos funcionaría,  veamos cómo funciona:

## Pasos:

- Vamos a [*Github*](https://github.com/)
- Seleccionamos nuestro perfil y pinchamos en nuestros repositorios.

<img src="./content/profile.png" alt="profile" style="zoom:67%;" />

- Pinchamos en crear uno nuevo

<img src="./content/new-repo.png" alt="new-repo" style="zoom:50%;" />

- Creamos uno nuevo que lo podemos llamar *mytest*, le añadimos un *Readme* y que tenga Licencia de tipo *MIT License*.

​					<img src="./content/create-repo.png" alt="create-repo" style="zoom:50%;" />

- Clonamos el repositorio

<img src="./content/clone-repo.png" alt="clone-repo" style="zoom:50%;" />

- Nos vamos a *Visual Studio Code*, hacemos *CTRL + SHIFT + P* o View--> Command Palette. Escribimos *Git:Clone* e introducimos la dirección del repo copiada anteriormente.

<img src="./content/clone-repo-code.PNG" alt="clone-repo-code" style="zoom:50%;" />

- Creamos una nueva rama llamada *gh-pages*

<img src="./content/gh-pages.PNG" alt="gh-pages" style="zoom:50%;" />

- Subimos esa rama a nuestro repo en *GitHub*

<img src="./content/create-github-branch.png" alt="create-github-branch" style="zoom:50%;" />

- Creamos un fichero HTML  y añadimos una cabecera.

*./index.html*

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Hello from my test Page!</h1>
  </body>
</html>
```

- Hacemos *commit* y *push* de nuestros cambios al repositorio.

<img src="./content/commit-html.PNG" alt="commit-html" style="zoom:50%;" />

-  Si queremos navegar a esta página y ver lo que hemos desplegado sería,

```bash
<perfilgithub>.github.io/mytest
```

<img src="./content/deploy.png" alt="deploy" style="zoom:80%;" />

Esto es muy útil para subir un proyecto en vivo y mostrar la demo.