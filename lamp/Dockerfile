FROM php:8.1-apache
LABEL org.opencontainers.image.authors="tingold"
LABEL org.opencontainers.image.source = "https://github.com/earthrise-media/base-images"

RUN docker-php-ext-install mysqli && \
    docker-php-ext-enable mysqli && \
    docker-php-ext-install exif && \
    docker-php-ext-enable exif && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y libpng-dev libfreetype6-dev libjpeg62-turbo-dev libgd-dev libpng-dev git libwebp-dev && \
    a2enmod rewrite && \
    docker-php-ext-configure gd \
        --with-freetype=/usr/include/ \
        --with-jpeg=/usr/include/ --with-webp && \
    docker-php-ext-install gd

RUN apt-get install libicu-dev -y && \
    docker-php-ext-install intl && \
    docker-php-ext-enable intl