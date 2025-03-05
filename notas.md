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
