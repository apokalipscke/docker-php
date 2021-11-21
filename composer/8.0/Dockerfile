FROM php:8.0-cli

MAINTAINER Marc Lipscke

# install required software
RUN apt-get update && apt-get install -y \
   unzip \
   libicu-dev \
   git

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install php extensions
RUN docker-php-ext-install pdo pdo_mysql intl

WORKDIR /composer

ENTRYPOINT ["composer"]
