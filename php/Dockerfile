FROM php:7.2-fpm

MAINTAINER Rus Skazkin <ruslan@skazkin.su>
RUN apt-get update && apt-get install -y wget git unzip imagemagick libmagickwand-dev \
    && pecl install xdebug-2.7.1 imagick \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-enable xdebug imagick

ADD ./php.ini /usr/local/etc/php/php.ini

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www