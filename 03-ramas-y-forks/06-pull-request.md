# Introducción

Mezclar ramas directamente desde terminal puede ser algo peligroso,
ya que hay veces en las que perdemos control sobre el código
que ese está mezclando.

Vamos a ver el concepto de Pull Request, esta funcionalidad la implementan
prácticamente la totalidad de DVCS que hay en la nube (Gitlab, Github,
Bitbucket, Azure Devops...)

# Manos a la obra

Sobre el repositorio que creamos previamente vamos a crear una nueba
rama

> Previo, nos aseguramos que estamos en máster y hacemos un pull

Vamos a crear una rama

```bash
git branch otrarama
```

```bash
git checkout otrarama
```

Vamos eliminar el _ficheroa.js_:

Vamos a insertar un nuevo fichero, _ficheroc.js_

_./ficheroc.js_

```js
console.log("fichero c");
console.log("***********");
```

Y vamos a modificar el ficherob:

_./ficherob.js_

```diff
console.log("*****************");
console.log("fichero II");
console.log("*****************");
+ console.log(`
+  Ala Celta a demostrar, por historia e tradición,
+  que o teu lema é nobre xogo, afouteza e corazón
+  Cando xogas con tesón, vibra toda a afección,
+  ala Celta berramos, ala Celta campión.
+ `)
```

Y vamos a comitear los cambios:

```bash
git add .
```

```bash
git commit -am "actualizaciones"
```

```bash
git push -u origin otrarama
```

Ahora en vez de mezclar la rama desde el terminal, vamonos al portal de git:

Abrimos una pull request de la nueva rama a master.

Ahora puedo ver todos los cambios que se han hecho, revisarlos y comentar
mejoras.

Aquí es importante, lo idea es que el revisor no cambie código, si no que
indique se puede mejorar o dudas, el dueño de la rama es quien debe aplicar
los cambios si aplican, así el desarrollador aprende.

# Conflictos...

Un tema muy interesante es el del manejo de conflictos, si los hay,
en una PR, lo que debemos de hacer siempre es mezclar de master a la rama
que queremos mezclar (Es decir al contrario de como hemos hecho hasta ahora),
esto se hace para ir limpios a master (el problema te lo comes en tu rama).

Como práctica podemos simular conflictos y ver como se ve en la PR.

Otro tema muy interesante es que podemos meter checks en las pull:

- Podemos poner que sólo ciertos usuarios tengan permisos para aprobar y
  mezclar a master.
- Podemos obligar a que una serie de revisores hayan aprobado la pull.
- Podemos meter pasos previos a la pull en la que automáticamente
  se lanze un build o tests y si no pasan que no se pueda hacer merge.
