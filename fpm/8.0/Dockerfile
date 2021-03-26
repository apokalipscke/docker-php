FROM php:8.0-fpm

MAINTAINER Marc Lipscke

# install required software
RUN apt-get update && apt-get install -y \
   unzip \
   libicu-dev \
   libxslt-dev

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install php extensions
RUN docker-php-ext-install pdo pdo_mysql intl xsl

# install xdebug
RUN pecl install xdebug-3.0.3 \
    && docker-php-ext-enable xdebug
