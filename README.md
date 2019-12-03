PKP UI Library para OJS 3.1.2 (SIDISI Revisión Académica)
=======

> Esta es una version personalizada de ui-library para SIDISI Revisión Académica. Esta versión de la librería es 3.1.2, que corresponse a la versión 3.1.2 de OJS. Asegurarse de trabajar en la rama stable-3_1_2-upch-rev-aca para esta versión, no confundir con stable-3_1_2 que es la rama original.

# Instalación en OJS (solo una vez)

Ejecutar en terminal en la carpeta de OJS:

    $ git checkout stable-3_1_2-upch-rev-aca
    $ git submodule add https://github.com/alvaro-ossio19/ui-library.git  lib/ui-library

Esto habrá agregado la librería como submodulo en OJS en el archivo .gitmodules:

[submodule "lib/ui-library"]
	path = lib/ui-library
	url = https://github.com/alvaro-ossio19/ui-library.git

# Agregar repositorio padre de lib/ui-library

Verificar los remotes de repositorio del proyecto en nuestro local:

    $ cd lib/ui-library
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

# Actualización con rama stable-3_1_2 del repositorio padre

Sincronizamos los repositorios remotos:

    $ git remote update

Si es la primera vez que iremos a la rama stable-3_1_2-upch-rev-aca del fork:

    $ git checkout --track origin/stable-3_1_2-upch-rev-aca

Para fusionar los cambios del repositorio padre desde upstream/stable-3_1_2 con la rama origin/stable-3_1_2-upch-rev-aca (fork):

    $ git checkout stable-3_1_2-upch-rev-aca
    $ git pull upstream stable-3_1_2
    $ git push

Vamos a la raíz de OJS para instalar o actualizar dependencias con [NPM](https://www.npmjs.com/):

    # install [nodejs](https://nodejs.org/en/) if you don't already have it
    $ cd ../..
    $ npm install
    $ npm run build

## Git Tags:

Para crear un tag, nos vamos a la rama stable-3_1_2-upch-rev-aca del fork:

    $ git checkout stable-3_1_2-upch-rev-aca
    $ git tag 'ojs-3_1_2-2_upch-rev-aca' -a
    $ git push --tags

## Sincronizar tags con upstream

Cuando salen nuevas versiones de lib/ui-library se registran nuevos tags en el repositorio padre. Para sincronizarlos con el fork:

    $ git fetch upstream
    $ git push
    $ git push --tags

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
