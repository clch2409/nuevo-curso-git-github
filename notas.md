# Curso de Git y GitHub

## Preparar cnofiguración inicial

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

  git add <filename> //Agrega el archivo al staging

  git add . //Agrega TODOD los archivos del repositorio que estén untracked a staging

  git rm --cached <filename> //Saca de staging al archivo y pasa a untracked

  git rm --force <filename> //Saca de sataging al archivo y lo ELIMINA

```

### Tomando en consideración

OJO -> Cuando hablamos de que los documentos están en STAGING, es que el archivo no se encuentra registrado en la carpeta .git de nuestro repositorio.

## Hacer commit de mis archivos

```bash
  git commit -m "mensaje" //El flag -m se refiere a message

  git commit -am "mensaje" //Agrega a staging aquellos archivos que ya estaban creados y se les hicieron cambios. Sin embargo, no agregan archivos recién creados a staging, se debe usar "git add"
```

¿Qué es un commit? -> Es un registro de los cambios realizados en los archivos de un repositorio

OJO -> Recordar que al hacer commit, estos son registrados en la carpeta.

## Utilizando ramas

```bash
  
  git branch //Muestra el listado de ramas y especifica en cuál nos encontramos en dicho momento

  git switch -c <nombre de rama> //Crea y te mueve a dicha rama

  git checkout -b <nombre de rama> //Crea y te mueve a dicha rama

```

## Unificando archivos

```bash
  git merge < rama donde quiero que vengan los cambios >
```
