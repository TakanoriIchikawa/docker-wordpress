FROM php:8.1-fpm

COPY ./docker/app/php.ini /usr/local/etc/php/php.ini
COPY ./docker/app/php-fpm.d/zzz-docker.conf /usr/local/etc/php-fpm.d/zzz-docker.conf
COPY ./docker/app/setup.sh /tmp

# Composer
COPY --from=composer:2.1 /usr/bin/composer /usr/bin/composer

# Node.js
COPY --from=node:16.0 /usr/local/bin /usr/local/bin
COPY --from=node:16.0 /usr/local/lib /usr/local/lib

# パッケージインストール
RUN apt update && \
    apt -y install \
    git \
    zip \
    unzip \
    vim \
    && docker-php-ext-install opcache \
    && docker-php-ext-install pdo_mysql bcmath

# wordpressでMySQLと接続するには下記が必要？どっちか一つでも良い？
RUN apt-get -q -y install default-mysql-client
RUN docker-php-ext-install mysqli

WORKDIR /var/www/html