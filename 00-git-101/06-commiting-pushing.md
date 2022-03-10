# Trabajo básico

Ahora que tenemos todo el *setup* montado, vamos a ir subiendo cambios.

# Manos a la obra

- Vamos a simular que estamos trabajando, introducimos un cambio en uno de los ficheros:

TODO: cambiar console.log

```tsx

```

- Si ahora intentamos hacer commit podemos ver que no tenemos nada que "commitear" ¿Por qué? Porque primero tenemos que marcar los cambios como listos para guardar en nuestra base de datos local, para ello los incluimos todos:

```bash
git add .
```

> Más adelante veremos en detalle como añadir sólo ciertos ficheros y cómo funciona
> el area de staging

Y ahora que si tenemos los cambios en local, y la rama main creada en el servidor, podemos subirlos a la nube:

```bash
git push
```
