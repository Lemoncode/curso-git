# Introducción

Migrar tu repositorio a otro servidor... ¿Por qué puede ocurrir esto?

- Si tienes tu propia infraestructura, puede que esta se haya quedado pequeña o te toque renovar un server que está un poco pachucho.
- Si estás en la nube, la principal razón es que te mueves de proveedor:
- Esto pasa cuando por ejemplo tu proyecto pasa a manos de un cliente (lo migras a su proveedor o cuenta)
- Esto lo hemos vivido en Lemoncode migrando de Bitbucket a Github (todavía hay algún repo coleando), por funcionalidad, costes,
  disponibilidad etc...

Con los repositorios antiguos tenías que hacer migraciones con tools que daban un poco de "respeto", sobre todo si no querías
perder el historico.

Con Git como tenemos la base de datos en local, es pan comido, veamos como.

# Ejemplo migración

## Preparación ejemplo

Partimos de que creamos un repositorio en Github con un readme.

> Crear repo con Readme.

Vamos añadir un commit de prueba

_./readme.md_

```diff
# Readme

+ texto añadido
```

```bash
git commit -am "actualizado readme"
```

```bash
git push
```

Y vamos a crear una rama y añadir un fichero de prueba

```bash
git branch mirama
```

```bash
git checkout mirama
```

_nuevo.txt_

```txt
Texto de prueba
```

Y ejecutamos los comandos:

```bash
git add .
```

```bash
git commit -m "nuevo fichero"
```

Vamos a subir todos los cambios a servidor

```bash
git push -u origin mirama
```

Genial ya tenemos nuestro repo en Github (podemos verlo en el navegador).

Vamonos a Gitlab y vamos crear un repositorio nuevo.

> Gitlab > Nuevo proyecto > ejemplo migracion

Vamos a empezar migrando:

me voy a nueva carpeta

```bash
mkdir migracion
```

```bash
cd migracion
```

Y hacmos un clon de nuestro repo original

```bash
git clone --mirror **Url repo github**
```

Entramos en la carpeta del proyecto clonado

```bash
cd <cloned folder>
```

- Y hacemos un push a la nueva url usango el flag _mirror_

git push --mirror **Url repo destino Gitlab**

Vamos a ver en Gitlab el proyecto, podemos clonarlo a local
y ver que tenemos las ramas y commits originales:

```bash
git log --pretty=oneline --abbrev-commit
```
