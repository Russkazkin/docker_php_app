FROM php:7.3-fpm

MAINTAINER Rus Skazkin <ruslan@skazkin.su>
RUN apt-get update && apt-get install -y wget git unzip imagemagick libmagickwand-dev zlib1g-dev libicu-dev g++ \
    && pecl install xdebug-2.7.1 imagick \
    && docker-php-ext-install pdo_mysql intl bcmath\
    && docker-php-ext-enable xdebug imagick intl

ADD ./php.ini /usr/local/etc/php/php.ini

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /usr/share/nginx/html