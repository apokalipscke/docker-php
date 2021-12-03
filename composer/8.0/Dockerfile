FROM php:8.0-cli-alpine

MAINTAINER Marc Lipscke

# install required software
RUN apk update && apk add \
   unzip \
   icu-dev \
   git

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install php extensions
RUN docker-php-ext-install pdo pdo_mysql intl

WORKDIR /composer

ENTRYPOINT ["composer"]
