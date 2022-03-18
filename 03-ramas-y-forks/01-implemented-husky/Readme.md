# Instalación de husky
Imaginemos que estamos trabajando en equipo y todo el mundo está subiendo código a ese repositorio. Tendríamos la
problemática que cuando el proyecto vaya creciendo el código estaría mal formateado y sería cada vez menos legible.
Husky es una herramienta que mejora nuestros _Git hooks_, y en este caso vamos a utilizarlo para que nos formatee el código cada vez que hacemos un _commit_ a nuestro repositorio.

## Pasos

- Con el siguiente comando instalamos  _husky_ y su carpeta de configuración.

[Documentación](https://prettier.io/docs/en/precommit.html)

```
npx husky-init
```
- Instalamos _prettier_ y que nos formateará el código y _pretty_quick_ que nos ejecuta _Prettier_ en los archivos que hayamos modificado.

[Documentación prettier](https://www.npmjs.com/package/prettier)

[Documentación pretty_quick](https://www.npmjs.com/package/pretty-quick)

```
npm install prettier pretty-quick --save-dev
```
- Y por último cambiamos el archivo _pre-commit_ dentro de la carpeta _husky_ para que nos ejecute _pretty-quick_ cada vez que hacemos un _commit_ y quitamos por defecto que ejecute los test.

_.husky/pre-commit_
```diff
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

- npm test
+ npx pretty-quick --staged
```

