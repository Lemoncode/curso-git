# Jugando con staging

Hacer los pasos perfectos, está bien, pero somos humanos y de cuando en
cuando metemos alguna cagada que otra, por ejemplo que pasemos a staging
un montón de ficheros temporales y nos quedemos con la cara de ¿Y ahora
que hago?...

En esta sección aprendemos a manejarnos con staging, pero no cubrimos
como deshacer commits, esto lo veremos en la sección de avanzado, ya que
este paso puede ser mucho más delicado.

Seguimos con el ejemplo anterior de repositorio local (también valdría
otro anterior que tengas abierto)

Vamos a crear un fichero que se llame

_./src/temporal.txt_

```text
Soy un fichero temporal
```

_./src/definitivo.txt_

```text
Soy un fichero definitivo
```

Andamos un poco despistados y añadimos ambos ficheros a staging

```bash
git add .
```

Cuando hacemos un _git status_ nos damos cuenta de la cagada :-@

```bash
git status
```

Aquí tenemos dos soluciones, si son un porrón de ficheros, igual
recoger carretes y quitar de staging todos los ficheros (botón
de pánico):

```bash
git reset
```

Si es sólo un fichero, podemos indicarle directamente el fichero
a pasar de staging a modificado:

```bash
git reset HEAD ./src/temporal.txt
```

Si ahora hacemos un git status podemos ver que sólo esta en staging el
fichero que esperabamos.

Veamos otro caso

Volvemos al casillero inicial:

```bash
git reset
```

Y vamos a modificar el fichero _index.html_

```diff
<html>
  <body>
-    <h1>Ola Git</h1>
+    <h1>Aqui va un cambios</h1>
    <script src="./index.js"></script>
  </body>
</html>
```

Si hacemos un _git status_ podemos ver que hay dos ficheros nuevos,
y uno existente con modificaciones, los tres no están en el area
de staging.

```bash
git status
```

Imaginemos que todo el trabajo que hemos hecho eran pruebas tontas,
y queremos volver al punto inicial en el que estabamos, en este
caso tenemos dos comandos a mano.

El primero devuelve al estado inicial los ficheros trackeados, es decir pierdes
las modificaciones, PEEERO no toca los ficheros que son nuevos.

```bash
git checkout -- .
```

Si echamos un ojo a lo que ha pasado:

```bash
git status
```

Tenemos que _index.html_ a vuelto al estado inicial.

Y los fichero nuevos, al no estar en la rama incial se quedan como estan.

Vamos a probar un segundo comando más rádical, imaginate que has estado
jugando con tu rama y tienes cosas en stage, otras que no, ficheros nuevo...
pero es todo tan desastroso que dices "mira quiero volver al punto inicial
y cargarme tooooodooos los cambios"

Primero preparamos el terreno:

```bash
git status
```

Vamos a modificar el fichero index.html.

Vamos a mandar a staging el fichero definitivo.txt

```bash
git add src/definitivo.txt
```

Si lo hemos hecho bien tendremos ficheros tanto en stage como no,
así como fichero que si estaban en el commit de partida.

Si ejecutamos _restore_

```bash
git restore
```

> Si te sale este error _git: 'restore' is not a git command._ puedes que tenga una versión antigua de Git, para saber en que versión estás ejecuta
> _git --version_

# Referencias

[Unstage files on Git](https://devconnected.com/how-to-unstage-files-on-git/)

[Git restore](https://git-scm.com/docs/git-restore)
