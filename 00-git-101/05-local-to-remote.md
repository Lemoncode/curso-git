# De local a la nube

Ahora que tenemos nuestro repositorio y nuestro acceso al mismo
desde nuestra máquina local establecido, toca interactuar con
el repositorio...

Partimos de un repositorio en local, vamos a conectarlo con el repositorio
a la nube y enviar cambios...

# Manos a la obra

Tenemos nuestro repositorio creado en local, vamos ahora a conectarlo
con el que hemos creado en la nube, para ello nos vamos al terminal
(en la carpeta en la que lo hemos creado), y le añadimos como _origin_
remoto la *url* del repo en la nube.

```bash
git remote add origin git@....
```

Ahora que lo hemos añadido sólo tenemos que subir la rama local que tenemos
al repo

> Nota ver si es master o main

```bash
git push -u origin master
```
