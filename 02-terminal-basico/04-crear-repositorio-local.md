# Arrancando de local

Un escenario muy habitual es que estamos trabajando en nuestro proyecto en
local y decidimos subirlo a Github (un consejo para los que tenéis alumnos
si están trabajando en una práctica entregable que arranquen directamente
con un repositorio y vayan subiendo cambios al mismo, nunca sabes cuando
se te va a romper el disco duro, o vas a cargarte un código que funcionaba).

Vamos a simular que creamos un proyecto sin tener en cuenta git, creamos una
carpeta _miproyecto_ y vamos a introducir algunos ficheros (esta parte
no tiene que ver con Git)

_./src/index.html_

```html
<html>
  <body>
    <h1>Ola Git</h1>
    <script src="./index.js"></script>
  </body>
</html>
```

_./src/index.js_

```js
console.log("¡ Hola Git!");
```

_./package.json_

```json
{
  "name": "01-basic",
  "version": "1.0.0",
  "description": "Let's start with a very basic sample, just add an html plus a simple console log (E5). This is what you can find in the getting started tutorial.",
  "main": "index.js",
  "scripts": {
    "build": "rimraf dist && parcel ./src/index.html",
    "build:prod": "rimraf dist && parcel build ./src/index.html",
    "start": "rimraf dist && parcel ./src/index.html --open"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "parcel-bundler": "^1.12.4",
    "rimraf": "^3.0.2"
  }
}
```

_./readme.md_

```md
# Desde local
```

Bueno, ahora que tenemos todos los ficheros, vamos a ejecutar esta aplicación
tonta,... para ello os va a hacer falta instalaros _nodejs_ (https://nodejs.org/es/)

Cerramos terminales por si acaso.

Y ahora vamos a instalar librerías de terceros y ejecutar el proyecto
(nos vamos a la carpeta en la que se encuentra el fichero _package.json_):

```bash
npm install
```

```bash
npm start
```

Perfecto, nuestro proyecto está funcionando, ... no sería mala idea
subirlo a Github antes de que la caguemos no? Ya no vale la excusa
aquella de "el perro se comió los apuntes".

De primeras vamos a inicializar un repo en local:

```bash
git init
```

Fijate que ahora nos aparece la carpeta oculta _.git_, ahí esta nuestro
proyecto.

Vamos a commitear los cambios a nuestro repo local, primero tiramos de 
un git status y.... 

```bash
git status
```

¡ Sorpresa !


