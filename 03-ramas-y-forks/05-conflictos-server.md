# Introducción

Hasta ahora hemos estado trabajando en un repositorio local, vamos
a ver como manejar conflictos si estamos conectado a uno repositorio
en la nube.

# Pasos

Arrancamos con nuestro proyecto:

Vamos a crear una carpeta, podemos llamar _practica_

```bash
mkdir practica
```

```bash
cd practica
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

Antes de seguir vamos a conectar esto con un repo en Github,
para ello:

- Creamos el proyecto en Github.
- Copiamos la url (depende de si estás con https o ssh) para
  clonar

Vamos añadirlo como origin a nuestro repo:

```bash
git remote add origin https://github.com/...
```

```bash
git push --set-upstream origin master
```

Ya tenemos el repo conectado (navegamos al portal
de github y en efecto vemos que todo se ha subido)

Vamos ahora a replicar el issue del conflicto, para ello
lo interesante es que un alumno se ponga en su maquina:

Lo primero le voy a dar permiso al alumno de lectura y
escritura (que pasaría si no, la ser publico funcionaría
la bajado pero no la subida)

**Alumno clona repo en su maquina**

```bash
git clone https://github.com/...
```

El alumno crea rama en local:

```bash
git branch mirama
```

```bash
git checkout mirama
```

_ficheroa.js_

```diff
- console.log("*****************");
+ console.log("+++++++++++++++++");
console.log("soy el fichero a");
- console.log("*****************");
+ console.log("+++++++++++++++++");
```

_ficherob.js_

```diff
- console.log("*****************");
+ console.log("-----------------");
- console.log("soy el fichero b");
+ console.log("soy el segundo fichero");
- console.log("*****************");
+ console.log("-----------------");
```

vamos a subir los cambios

```bash
git commit -am "actualizacion contenido"
```

Si queremos podemos subirlo a servidor

```bash
git push -u origin mirama
```

Ahora saltamos a la maquina del profesor

**Comparte el profesor**

Yo sigo en master y cambio lo siguiente:

_ficherob.js_

```diff
console.log("*****************");
- console.log("soy el fichero b");
+ console.log("fichero II");
console.log("*****************");
```

Y hacemos commit del cambio:

```bash
git commit -am "actualizacion segundo fichero"
```

y subo lo cambios a servidor

```bash
git push
```

Vamos a saltar a la parte del alumno:

** Vuelve a compartir el alumno **

Queremos mezclar los cambios de mi rama a master, lo primero que
hago es saltar a master,

```bash
git checkout master
```

Ahora podríamos estar tentados de mezclar, Peeeero si mezclamos
lo estamos haciendo contra un commit antiguo de master, vamos a
bajarnos la ultima versió de la rama:

```bash
git pull
```

Y ahora si intentamos mezclar:

```bash
git merge mirama -m "mezclando mirama"
```

Vemos que tenemos el conflicto, lo arreglamos.

Ya estamos listos para comitear:

```bash
git commit -m "mezclando mi rama"
```

Y subir los cambios a servidor

```bash
git push
```

En el lado alumno te puedes hacer un pull y ve que están los cambios

**_Alumno_**

```bash
git checkout master
```

```bash
git pull
```

# Git Pull vs Fetch

Git pull se baja cambios y modifica tu corte en local (puede
lanzar un merge en tu rama en checkout), esto suele ser lo normal que tu necesitas (git pull lo que hace es un fetch y una acción adicional,
normalmente un merge)

Git fetch, se baja los cambios de tu remoto, pero no hace
cambios en tu local (es decir actualiza las ramas remotas, pero
las locales enlazadas se quedan como está).

Más informacíon: https://www.gitkraken.com/learn/git/problems/git-pull-vs-fetch

En español: https://geekytheory.com/diferencia-entre-git-pull-y-git-fetch/

Git Fetch en detalle: https://www.atlassian.com/es/git/tutorials/syncing/git-fetch

Git Pull en detalle: https://www.atlassian.com/es/git/tutorials/syncing/git-pull
