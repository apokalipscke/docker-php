# Docker PHP Image

## Contents
- composer
- git

**PHP Extensions**
- xdebug (except :[version]-composer)
- xsl (except :[version]-composer)
- intl
- pdo
- pdo_mysql

## Tags
### [version]-composer
- `8.2-composer`, `latest-composer`
- `8.1-composer`
- `8.0-composer`

#### Usage
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
Installs the dependency inside your current location.

### [version]-fpm
- `8.2-fpm`, `latest-fpm`, `latest`
- `8.1-fpm`
- `8.0-fpm`

#### usage
docker-compose.yml
```yaml
version: "3.8"

services:
  web:
    image: nginx:1.19
    container_name: my-project-web
    ports:
      - 80:80
    volumes:
      - ./web/my-project.dev.conf:/etc/nginx/conf.d/default.conf
      - ./src:/var/www/application
      - ./web/logs:/var/log/nginx
    networks:
      - my-project-network

  php:
    image: apokalipscke/php:7.4-fpm
    container_name: my-project-php
    volumes:
      - ./src:/var/www/application
    networks:
      - my-project-network

networks:
  my-project-network:
    driver: bridge
```