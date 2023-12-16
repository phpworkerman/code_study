FROM php:8.3-fpm

RUN apt-get update && apt-get install -y \
		libfreetype-dev \
		libjpeg62-turbo-dev \
		libpng-dev \
        libzip-dev

RUN docker-php-ext-install gd bcmath pcntl zip pdo_mysql

RUN pecl install redis-6.0.2 \
	&& pecl install xdebug-3.3.1 \
    && pecl install xlswriter-1.5.5 \
	&& docker-php-ext-enable redis xdebug xlswriter

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html
