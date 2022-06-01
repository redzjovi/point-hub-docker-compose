ARG VERSION 

FROM php:${VERSION}-fpm

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    zip

RUN docker-php-ext-install \
    gd \
    pcntl \
    pdo_mysql \
    zip

ARG INSTALL_GRPC=false
RUN if [ ${INSTALL_GRPC} = true ]; then \
    pecl install grpc && \
    docker-php-ext-enable grpc \
;fi

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

ARG PUID=1000
ENV PUID ${PUID}
ARG PGID=1000
ENV PGID ${PGID}

RUN groupmod -o -g ${PGID} www-data && \
    usermod -o -u ${PUID} -g www-data www-data

EXPOSE 9000
