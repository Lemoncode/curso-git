# Introdución

Cando traballamos nun proxecto open source, é normal que se den casos
tales como que haxa centos de colaboradores, ou colaboradores que non 
coñecemos de nada, imaxinaste xestionar permisos neses casos?
Sería complicado e podería abrir brechas de seguridade.

Vamos a ver como funciona o "fork" dun proxecto, cun caso práctico.

# Manos a la obra

- Imaginemos que hay un grupo de voluntarios que quieren añadir al repo
  del curso de git versiones de las guias en Gallego, van a haber
  17 colaboradores, ¿Cómo podemos gestionar esto?

- A nivel de gestión, podríamos crear un issue por cada fichero,
  el propio colaborador puede proponerlo (crear un issue).

- El colaborador puede "forkear" el repo, ¿Esto que es?

  - Se te crea en tu area de Github un repositorio con una copia
    del repositorio original (como si fuera una fotocopia).
  - Ese repositorio apunta a dos servidores el que acabas de
    fotocopiar y el original.

- En ese proyecto tu puedes trabajar como mejor te venga (creando
  ramas, o en master, etc...).

- Imaginenmos que nos ponemos manos a la obra, terminamos el fichero
  nuevo con sufijo -gl para indicar que es la versión en Gallego.

- A la hora de hacer el commit vamos a referencia el issue con el
  siguiente comentario

```bash
git add .
```

> Cambiar 10 por el id del issue

```bash
git commit -am "closes #10"
```

> Nota puede que al estar forkead te haga flata referenciar el repo
> completo (octo-org/octo-repo#100)

- Si ya estamos listos, puedo pedir pull request al repositorio original
  (a partir de ahora lo llamaremos al repositorio pata negra).

- En el caso del usuario forkeado no podrá mezclar la pull.

- El administrador / mantenedores del proyecto original pueden
  revisar y mezclar la rama.
