# https://hub.docker.com/_/php
FROM php:8.0.8-fpm-buster

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    # Using git for development.
    git \
    # libzip-dev: enable PHP zip extension with `docker-php-ext-install zip` command.
    zip unzip libzip-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN pecl install xdebug-3.0.4 \
    && docker-php-ext-install zip \
    && docker-php-ext-enable xdebug

# Composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php composer-setup.php --version=2.1.3 --install-dir=/usr/local/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"
