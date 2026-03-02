FROM php:8.3.19-fpm
RUN apt-get update && apt-get install -y \
    nano \
    zip \
    unzip \
    curl \
    && docker-php-ext-install \
    pdo \
    pdo_mysql \
    bcmath \
    ftp \
    sockets \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html
COPY src/monitoring/ .

WORKDIR /var/www/html/laravel
COPY env/laravel/.env .env
RUN composer install

RUN chown -R www-data:www-data storage \
    && chown -R www-data:www-data bootstrap/cache \
    && chmod -R 775 storage \
    && chmod -R 775 bootstrap/cache

CMD ["php", "artisan", "migrate", "--seed"]