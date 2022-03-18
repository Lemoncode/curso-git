# Introducción

Meter la pata es algo muy normal, vamos con prisas y hacemos un commit de algo que no deberíamos de haber hecho...

¿Solución? ... Ir con cuidado, como hemos visto antes, en Git los commits van en una lista enlazada, si borramos
un commit si tener cuidado podemos liarla parda.

Aquí vamos a distinguir tres casos:

- Cuando quiero borrar un commit en local y todavía no lo he subido al servidor.
- Cuando quiero borrar un commit que he subido a servidor, pero todavía nadie ha estado trabajando con el.
- Cuando quiero borrar un commit que he subido a servidor, pero que puede que otros usuarios hayan trabajado con él.

# Manos a la obra

## Preparando la demo

- Creamos un repositorio en blanco en github, con un readme.

- Vamos a clonarlo.

- Metemos un fichero temporal por equivocación, hacemos add y commit en local

- Y ... punto de partida.

## Borrando un commit en local

Si he hecho el commit en local, sabemos que es la cabeza de rama y no está relacionado con otro commit, podemos
tirarlo para atrás ejecutando un comando.

> Crear repo en github con readme >> bajar repo >> crear fichero temporal >> add + commitear local

Primero vamos a ver en que estado estamos:

```bash
git log --pretty=oneline --abbrev-commit
```

Vamos a eliminar este commit

```bash
git reset –hard HEAD~
```

Vamos a ver como ha quedado la cosa:

```bash
git log --pretty=oneline --abbrev-commit
```

## Borrando un commit que ya está en servidor

# Caso A - Justo subido pero nadie lo usa

Volvemos a añadir un fichero temporal, y esta vez hacemos commit y push.

> crear fichero temporal >> add + commitear local

Y pusheamos:

```bash
git push
```

Podemos ver el cambio en Github.

Nadie más está tocando esa rama así que veamos que podemos hacer.

Repetimos el cambio en local:

```bash
git reset --hard HEAD~
```

Y forzamos un push a esa rama

```bash
git push origin master
```

Vamos a ver github y ya no tenems ese commit

# Caso B

Si ya tenemos el commit subido y hay otros que beben de él, debemos tener mucho cuidado
borrando el commit, una opción es compensar el commit ¿Comoooor? Si crear un commit que
justo deshaga los cambios que ha introducido el otro commit, esto se hace commit
revert.

Volvemo a meter la pata, comitear y pushear...

> Crear repo en github con readme >> bajar repo >> crear fichero temporal >> add + commitear local

Pero esta vez le ponemos un commit por encima... con algo que si está bien

_./readme.md_

```diff
# prueba-borrar

texto bueno
```

_./nuevo-bueno.txt_

```
Este fichero es bueno
```

Y para arriba

```diff
git add .
```

```diff
git commit -m "Commit bueno"
```

```diff
git push
```

Vemos como queda la cosa

```bash
git log --pretty=oneline --abbrev-commit
```

Vamos a hacer un revert de ese commit (OJO EL PENULTIMO, EL MALO):

```bash
git revert **AñadirAquiSHACommit**
```

Veamos el log como ha quedado:

```bash
git log --pretty=oneline --abbrev-commit
```

Y podríamos hacer push y vemos en servidor que esta todo ok

```bash
git push
```

Vamonos a Github y lo comprobamos.

## Borrando contenido

Si realmente queremos borrar el contenido de los ficheros de la BBDD de Git podemos reescribir la
historia, pero esto puede llevarte a nuevos problemas.

https://stackoverflow.com/questions/50675829/remove-node-modules-from-git-in-vscode
