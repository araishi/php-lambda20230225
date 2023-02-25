FROM php:8.0-fpm
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

# timezone environment
ENV TZ=UTC \
    # locale
    LANG=en_US.UTF-8 \
    LANGUAGE=en_US:en \
    LC_ALL=en_US.UTF-8 \
    # composer environment
    COMPOSER_ALLOW_SUPERUSER=1 \
    COMPOSER_NO_INTERACTION=1 \
    COMPOSER_HOME=/composer

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update && \
    apt-get install -y \
        git \
        vim \
        libicu-dev \
        libonig-dev \
        libzip-dev \
        unzip \
        locales \
        default-mysql-client \
        default-libmysqlclient-dev \
		procps \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN locale-gen en_US.UTF-8 && \
    localedef -f UTF-8 -i en_US en_US.UTF-8

RUN pecl install redis

RUN docker-php-ext-install \
        mysqli \
        pdo_mysql
#        redis

COPY ./docker/php/www.conf /usr/local/etc/php-fpm.d/www.conf
COPY ./docker/php/php.ini /usr/local/etc/php/php.ini
