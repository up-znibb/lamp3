FROM php:7.4-apache

LABEL MAINTAINER="Emil Malm <emilamalm@gmail.com>"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

RUN apt-get install nano

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY ./php.ini /usr/local/etc/php/php.ini

COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf

RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mysqli posix

RUN a2enmod rewrite