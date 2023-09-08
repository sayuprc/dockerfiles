FROM php:7.3-apache

WORKDIR /var/www/html

RUN apt update -y \
  && apt install -y unzip libpq-dev git vim \
  && pecl install xdebug-3.1.5 \
  && docker-php-ext-enable xdebug \
  && docker-php-ext-install pgsql pdo_pgsql opcache \
  && a2enmod rewrite

COPY --from=composer /usr/bin/composer /usr/bin/composer
