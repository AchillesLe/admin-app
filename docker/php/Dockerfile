ARG WITH_XDEBUG=false

FROM php:7.4-fpm

# ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y libzip-dev

# Install composer
RUN curl -sS https://getcomposer.org/installer \
    | php -- --install-dir=/usr/local/bin --filename=composer

# Install nodejs
RUN apt-get install -y \
        nodejs \
        npm

# Install Xdebug
# RUN yes | pecl install xdebug-2.9.4 \
# 	&& docker-php-ext-enable xdebug

# Install Opcache
# RUN docker-php-ext-install opcache

# Install pdo_mysql , mysqli
RUN docker-php-ext-install pdo_mysql mysqli

# Install redis

# RUN pecl install redis \
#     && docker-php-ext-enable redis
CMD ["php-fpm"]

EXPOSE 9000