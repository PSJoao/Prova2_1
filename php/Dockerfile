FROM php:8.2-apache

ENV DEBIAN_FRONTEND=noninteractive

COPY apachando.conf /etc/apache2/sites-available/000-default.conf

RUN apt-get update && apt-get install -y \
    && docker-php-ext-install mysqli pdo pdo_mysql \
    && docker-php-ext-enable mysqli pdo pdo_mysql \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN chown -R www-data:www-data /var/www/html/
RUN chmod -R 755 /var/www/html


EXPOSE 80