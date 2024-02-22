FROM php:8.2.9-fpm

RUN apt-get update \
    && apt-get install -y \
        git \
        unzip \
        libzip-dev \
    && docker-php-ext-install \
        pdo_mysql \
        zip

COPY . /var/www/html

WORKDIR /var/www/html

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer install

EXPOSE 9000

