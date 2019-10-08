# Use an official PHP runtime as a parent image
FROM php:7.3-apache-stretch

ARG DEBIAN_FRONTEND=noninteractive

# Install any needed packages
RUN apt-get update -yqq && \
  apt-get install -yqq --no-install-recommends \
    apt-utils \
    openssl \
    libzip-dev zip unzip \
    git \
    mariadb-client \
    libpng-dev
RUN docker-php-ext-configure zip --with-libzip
RUN docker-php-ext-install pdo_mysql zip
RUN docker-php-ext-configure gd
RUN docker-php-ext-install gd


ENV COMPOSER_ALLOW_SUPERUSER 1
#ENV APACHE_DOCUMENT_ROOT /var/www/html/public

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
RUN a2enmod rewrite

USER root

# Clean up
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog

RUN usermod -u 1000 www-data

COPY *.js /var/www/html/
COPY *.php /var/www/html/
COPY *.css /var/www/html/

RUN chmod -R a+r /var/www/html


