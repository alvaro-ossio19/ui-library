PKP UI Library para OJS 3.1.2 (SIDISI)
=======

> Esta es una version personalizada de ui-library para SIDISI. Esta versión de la librería es 3.1.2, que corresponse a la versión 3.1.2 de OJS.

# Instalación

Ejecutar en terminal en la carpeta de OJS:

    $ git submodule add https://github.com/alvaro-ossio19/ui-library.git  lib/ui-library

Esto habrá agregado la librería como submodulo en OJS en el archivo .gitmodules:

[submodule "lib/ui-library"]
	path = lib/ui-library
	url = https://github.com/alvaro-ossio19/ui-library.git

Verificar los repositorios remotos del proyecto:

    $ git remote -v
    > origin  https://github.com/alvaro-ossio19/ui-library.git (fetch)
    > origin  https://github.com/alvaro-ossio19/ui-library.git (push)

Si no existe el repositorio original, hacer lo siguiente:

    $ git remote add upstream https://github.com/pkp/ui-library.git

Volvemos a verificar los repositorios remotos:

    $ git remote -v
    > origin        https://github.com/alvaro-ossio19/ui-library.git (fetch)
    > origin        https://github.com/alvaro-ossio19/ui-library.git (push)
    > upstream      https://github.com/pkp/ui-library.git (fetch)
    > upstream      https://github.com/pkp/ui-library.git (push)

# Actualización con repositorio padre

Vamos a la rama stable-3_1_2 (bifurcación):

    $ git remote update
    $ git fetch
    $ git checkout --track origin/stable-3_1_2

Para fusionar los cambios del repositorio padre desde upstream/stable-3_1_2 con la rama origin/stable-3_1_2 (bifurcación):

    $ git pull upstream stable-3_1_2
    $ git push

Vamos a la raíz de OJS para instalar o actualizar dependencias con [NPM](https://www.npmjs.com/):

    # install [nodejs](https://nodejs.org/en/) if you don't already have it
    $ cd ../..
    $ npm install
    $ npm run build

# PKP UI Library

A design pattern and component library for Public Knowledge Project's applications [Open Journal Systems](https://pkp.sfu.ca/ojs/) and [Open Monograph Press](https://pkp.sfu.ca/omp/).

## About

This library contains design patterns implemented or planned for the Public Knowledge Project's applications [Open Journal Systems](https://pkp.sfu.ca/ojs/) and [Open Monograph Press](https://pkp.sfu.ca/omp/).

This library can also be run locally to provide a style guide and sandbox environment for component development and testing. The style guide is intended to help orient developers to the existing components, outline markup guidelines, and provide details on how to adhere to accessibility requirements.

The style guide components are for demonstration purposes. In most cases, they are not fully functional and do not provide complete documentation. You should consult the source code for these components.

## Usage

This library is intended to be included and used within PKP's applications. It can also be run locally as a standalone app to develop and test components, and provide implementation guidance.

To get started:

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev
```

## Issues

Please file any development issues or questions with the [pkp/pkp-lib](https://github.com/pkp/pkp-lib) repository.
