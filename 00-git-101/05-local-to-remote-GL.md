# De local á nube

Agora que temos o noso repositorio e o noso acceso ao mesmo desde a nosa máquina local establecido, toca interacturar co repositorio...

Partimos dun repositorio en local, vamos conectalo co repositorio na nube e enviar cambios...

# Mans á obra

Temos o noso repositorio en local, vamos agora a conectalo co que creamos na nube, para iso vamos ao terminal (no cartafol no que o creamos), e engadimoslle como _origin_ remoto a *url* do repo na nube.

```bash
git remote add origin git@....
```
Agora que o engadimos só temos que subir a _branch_ local que temos ao repo.

> Nota: ver se é master ou main

```bash
git push -u origin master
```
