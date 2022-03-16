# Introducción

# Manos a la obra

Vamos a crear nuestro repo favorito:

Vamos a crear una carpeta, podemos llamar _practica_

```bash
mkdir mistash
```

```bash
cd mistash
```

Vamos a inicializar nuestro proyecto de Git:

```bash
git init
```

Y creamos dos ficheros:

_ficheroa.js_

```js
console.log("*****************");
console.log("soy el fichero a");
console.log("*****************");
```

_ficherob.js_

```js
console.log("*****************");
console.log("soy el fichero b");
console.log("*****************");
```

Vamos a comitear esto en local en la rama master:

```bash
git add .
```

```bash
git commit -m "ficheros iniciales"
```

Vamos a crear una rama y empezamos a trabajar en una modificacion:

```bash
git branch mirama
```

```bash
git checkout mirama
```

_ficherob.js_

```diff
console.log("*****************");
console.log("soy el fichero b");
console.log("*****************");
+console.log("Esto es una prueba");
```

De repente nos dicen que saltemos urgentemente a master y nos pongamos
a arreglar un bug, tenemos trabajo a medias que no queremos comitear,
vamos a soltarlo en un stash

```bash
git stash
```

```bash
git checkout master
```

Ok, bug arreglado, es hora de volver a _mirama_ y recupar el stash
y seguir trabajando:

```bash
git checkout mirama
```

Fijate que en _mirama_ no estan los cambios temporales, para recuperarlos
hago un:

```bash
git stash pop
```

Git stash tiene más funcionalidad, podemos utilizar "apply" en vez de pop
si queremos mantener el cambio en la lista de stash, también podemos
tener una lista de cambios de stash a aplicar (ver referencia).

# Referencia

Git Stash en detalle: https://www.atlassian.com/es/git/tutorials/saving-changes/git-stash
