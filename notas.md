# Curso de Git y GitHub

## Preparar configuración inicial

```bash

  git config --global init.defaultbranch main

  git config --global user.name "nombre de usuario"

  git config --global user.email "email del usuario"

```

## Crear un repositorio

```bash
  git init
```

## Agregar o quitar de estaging

```bash

  git add < filename > //Agrega el archivo al staging

  git add . //Agrega TODOS los archivos del repositorio que estén untracked a staging

  git rm --cached < filename > //Saca de staging al archivo y pasa a untracked

  git rm --force < filename > //Saca de sataging al archivo y lo ELIMINA

```

### Tomando en consideración

OJO -> Cuando hablamos de que los documentos están en STAGING, es que el archivo no se encuentra registrado en la carpeta .git de nuestro repositorio. Sino que se encuentra "trackeado" o el mismo control de versiones (git), conoce su existencia (por decirlo de alguna manera).

## Hacer commit de mis archivos

```bash

  git commit -m "mensaje" //El flag -m se refiere a message

  git commit -am "mensaje" //Agrega a staging aquellos archivos que ya estaban creados y se les hicieron cambios. Sin embargo, no agregan archivos recién creados a staging, se debe usar "git add"

```

¿Qué es un commit? -> Es un registro de los cambios realizados en los archivos de un repositorio

OJO -> Recordar que al hacer commit, este queda registrado en la carpeta .git

## Utilizando ramas

```bash
  
  git branch //Muestra el listado de ramas y especifica en cuál nos encontramos actualmente

  git switch -c < nombre de rama > //Crea y te mueve a dicha rama

  git checkout -b < nombre de rama > //Crea y te mueve a dicha rama

  git branch -d < nombre de rama > //Elimina la rama deseada

```

## Unificando archivos

```bash

  git merge < rama donde quiero que vengan los cambios > //Tomar en consideración que debemos de estar seguros de que la rama en la que nos encontremos, es la rama principal de nuestro proyecto o una rama a la que deseemos obtener los cambios de la otra rama

```

## Volviendo al pasado

```bash
  git reset --hard < hash del commit > //Se vuelve al commit que deseamos, al usar el flag "hard", los archivos de los nuevos commits se pierden.

  git reset --soft < hash del commit > //Regresamos al commit deseado, sin embargo, no se pierden los archivos nuevos creados o modificados.

  git reset --mixed < hash del commit > //Regresamos al commit deseado, sin embargo, los archivos nuevos creados hasta ese commit se toman como fuera del area de staging

  git revert < hash del commit > //Se hace un nuevo commit, a partir del hash de un commit anterior
```

## Agregando tags y regresando a commits anteriores

```bash

  git tag -a < nombre del tag > -m "mensaje adicional" //Agrega un tag al commit actual

  git tag -a < nombre del tag > < hash del commit > //Agrega un tag al commit deseado

  git show < nombre del tag > //Muestra con detalle la información del commit al que se le agregó dicho tag

  git tag -d < nombre del tag > //Se elimina el tag deseado

  git checkout < hash del commit > //Permite regresar a un commit anterior

```

## Clonando un repositorio remoto

```bash

  git clone < url del repositorio en GitHub >

  git branch -M main
  git remote add origin < url del repositorio en GitHub > //Tomar en consideración que esta manera se debe de hacer cuando el repositorio está vacío y ya exista en local
  git push -u origin main

```

## Productos adicionales de Github

* ***GitHub Projects***: Permite crear plantillas para llevar un control de las actividades dentro de un proyecto de software, cada tarea que agreguemos podemos relacionarla a un repositorio, a una persona y ver cómo avanza dicha tarea de manera visual.

* ***[GitHub Codespaces](https://github.com/codespaces/new)***: Son pequeños contenedores en donde podemos ejecutar nuestro proyectos que tengamos en github, estos ayuda a que podamos trabajar de manera remota en cualquier dispositivo.

* ***[GitHub Gists](https://gist.github.com)***: Permite compartir pequeños trozos de código con compañeros y estos se encuentra relacionado a tu cuenta de GitHub.

* ***GitHub Pages***: Permite alojar páginas web desde un repositorio de GitHub.

## Proteger tus proyectos privados con Tokens

1. Crear un proyecto privado
2. Ir a la sección de opciones de tu cuenta e ir a "developer settings" (al final)
3. Crear un token con los permisos requeridos
4. Mandar el token a la persona que lo utilizará
5. Clonar el repositorio e ingresar las credenciales que se piden y en contraseña, colocar el token creado.

## Proteger los paquetes de un proyecto