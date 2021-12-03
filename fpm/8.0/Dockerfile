FROM php:8.0-fpm-alpine

MAINTAINER Marc Lipscke

# install required software
RUN apk update && apk add $PHPIZE_DEPS \
   unzip \
   icu-dev \
   libxslt-dev \
   git

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install php extensions
RUN docker-php-ext-install pdo pdo_mysql intl xsl

# install xdebug
RUN pecl install xdebug-3.0.3 \
    && docker-php-ext-enable xdebug
