FROM php:8.0-fpm-alpine

RUN apk update && apk add --no-cache \
    git \
    unzip \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd \
    && docker-php-ext-install pdo pdo_mysql

#RUN usermod -u 1000 www-data && groupmod -g 1000 www-data
#USER "1000:1000"

# Установите Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Установите зависимости
#COPY . /var/www/app
WORKDIR ${CONTAINER_PROJECT_LOCATION}

#RUN composer install

# Настройте права доступа
#RUN chown -R www-data:www-data /var/www/app && chmod -R 755 /var/www/app

EXPOSE 9000
CMD ["php-fpm"]