FROM php:7.4-fpm

RUN apt-get update \
    && apt-get install -y apt-transport-https zlib1g-dev g++ git libicu-dev zip libzip-dev zip libxml2-dev build-essential openssl libssl-dev libldb-dev libpng-dev \
    && apt-get upgrade -y \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip intl pdo_mysql opcache gd \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && curl -sS https://get.symfony.com/cli/installer | bash && mv /root/.symfony/bin/symfony /usr/local/bin/symfony \
    && apt-get autoremove -y

WORKDIR /var/www/app
