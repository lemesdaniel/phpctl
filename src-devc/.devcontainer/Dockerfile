FROM php:8.3-bookworm
COPY rootfs /
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libcurl4-openssl-dev libc-ares-dev libsqlite3-dev libpq-dev git unzip wget \
    && mv /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini \
    && mv /etc/php/php.ini /usr/local/etc/php/conf.d/zzphp.ini \
    && install-php-extensions sockets && install-swoole && install-tools
