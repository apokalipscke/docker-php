ARG PHP_VERSION

FROM php:${PHP_VERSION}-cli-alpine

MAINTAINER Marc Lipscke

# install required software
RUN apk update && apk add --no-cache unzip icu-dev git \
    && docker-php-ext-install intl

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /composer

ENTRYPOINT ["composer"]
