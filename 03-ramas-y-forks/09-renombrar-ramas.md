# Introducción

Hay veces que cuando creamos una rama nos damos cuenta de que
hemos metido la pata escribiendo el nombre de la rama, vamos
ver como renombrar una rama (teniendo cierto cuidado).

# Pasos

Lo primero **mucho cuidado** es buena idea renombrar una rama
si hay otros compañeros usandola, y mucho cuidado renombrando la rama
master :).

Esta vez vamos a crear un repositorio en Github y clonarlo,
metemos un readme.md para que tenga contenido.

> Siguiendo pasos anteriores crear repo renombre

Uha vez clonado

Vamos crear una rama, podemos llamar _malnombre_, actualizamos el readme,
añadimos, comiteamos y pusheamos.

```bash
git branch malnombre
```

```bash
git checkout malnombre
```

_./readme.md_

```diff
# borrar

+ Hola git
```

```bash
git commit -am "info readme"
```

```bash
git push
```

Ok, ya tenemos la rama en local y en servidor, nos hemos dado cuenta
que nos hemos equivocado nombrando la rama, aquí tenemos un problema
ya que en Git tenemos ramas en local y ramas en remoto, ¿Cómo podemos
hacer para remombrar ambas?

Veamos como ha quedado la cosa

```bash
git branch -a
```

vamos primero a cambiar el nombre de la rama en local:

```bash
git branch --move malnombre mirama
```

Comprobamos que en local ya esta bien pero en remoto no.

```bash
git branch -a
```

Y vamos ahora a actualizarlo en el repo en remoto:

```bash
git push --set-upstream origin mirama
```

Vams a ver como ha quedado la cosa:

```bash
git branch --a
```

En esta caso ya ha desparecido la rama _mala_ y tenemos la renombrada,
si no hiciera falta borrar una rama en servidor:

```bash
git push origin --delete malnombre
```

Realizar un renombre de una rama tan crítica como máster debe hacerse con cuidado,
asegurarte que tus scripts de CI/CD estan cambiados, que todos los que
colaboran estan al tanto...
