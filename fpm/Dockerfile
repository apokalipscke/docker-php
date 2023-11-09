ARG PHP_VERSION
ARG XDEBUG_VERSION

FROM php:${PHP_VERSION}-fpm-alpine

MAINTAINER Marc Lipscke

# install required software
RUN apk add --no-cache unzip git icu-dev libxslt-dev

RUN apk update && apk add --no-cache --virtual .build-deps autoconf g++ make linux-headers \
    && pecl install xdebug-${XDEBUG_VERSION:-'3.2.2'} \
    && docker-php-ext-install pdo pdo_mysql intl xsl \
    && docker-php-ext-enable xdebug \
    && apk del .build-deps

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
