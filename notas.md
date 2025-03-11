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

```

## Unificando archivos

```bash

  git merge < rama donde quiero que vengan los cambios >

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

```