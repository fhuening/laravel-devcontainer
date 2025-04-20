FROM php:8.2-apache

# System-Vorbereitung
RUN apt-get update && apt-get install -y \
    git unzip curl libzip-dev zip libpng-dev libonig-dev \
    libxml2-dev libpq-dev libjpeg-dev libfreetype6-dev \
    libjpeg62-turbo-dev libmcrypt-dev \
    libmemcached-dev zlib1g-dev gnupg \
    libcurl4-openssl-dev libssl-dev pkg-config \
    && docker-php-ext-install pdo pdo_mysql zip

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

# mod_rewrite aktivieren
RUN a2enmod rewrite

# Composer installieren
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Apache-Konfiguration überschreiben
COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf

COPY ./xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

# Arbeitsverzeichnis
WORKDIR /var/www/html

# Rechte setzen
RUN chown -R www-data:www-data /var/www/html

# Laravel Dependencies vorbereiten (optional, sonst composer install im postCreateCommand)

