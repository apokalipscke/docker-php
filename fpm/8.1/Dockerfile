FROM php:8.1-fpm-alpine

MAINTAINER Marc Lipscke

# install required software
RUN apk update && apk add autoconf g++ make \
   unzip \
   icu-dev \
   libxslt-dev \
   git

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install php extensions
RUN docker-php-ext-install pdo pdo_mysql intl xsl

# install xdebug
RUN pecl install xdebug-3.1.5 \
    && docker-php-ext-enable xdebug
