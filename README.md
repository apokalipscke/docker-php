# Docker PHP Image

## Contents
- composer

**PHP Extensions**
- xdebug (except :[version]-composer)
- intl
- pdo
- pdo_mysql

## Tags
`7.4-composer`, `latest-composer`

### Usage
**Creating a new project**
```shell
docker run --rm -it -v $PWD:/composer apokalipscke/php:latest-composer create-project symfony/skeleton my-project
```
Creates the directory 'my-project' at your current location,
creates a symfony skeleton project inside my-project, downloads dependencies and removes container.

**Install dependencies**
```shell
docker run --rm -it -v $PWD:/composer apokalipscke/php:latest-composer req apokalipscke/file-mimer
```
Installs the dependency inside you current location.