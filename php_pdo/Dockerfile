FROM php:7.0-fpm
RUN apt-get update && apt-get install -y \
        libicu-dev \
        libmcrypt-dev \
        mysql-client libmagickwand-dev --no-install-recommends \
    && docker-php-ext-install \
        intl \
        opcache \
    && pecl install imagick \
    && docker-php-ext-enable \
        intl \
        opcache \
        imagick \
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install bcmath

RUN apt-get install -y zip unzip zlib1g-dev libpng-dev
RUN docker-php-ext-install gd