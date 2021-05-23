FROM php:7.3-apache-stretch
RUN  pecl install xdebug-2.8.1 \
    && docker-php-ext-enable xdebug


RUN apt-get update && apt-get install -y nano git

RUN docker-php-ext-install mysqli
RUN docker-php-ext-enable mysqli

COPY ./apache2.conf /etc/apache2/apache2.conf

COPY ./docker-php.conf /etc/apache2/conf-enabled/docker-php.conf

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /srv/application