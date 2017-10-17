FROM php:7.1-fpm

# Install libraries
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      libicu-dev \
      libmagickwand-dev \
    && rm -r /var/lib/apt/lists/* 

# Install PHP extensions
RUN docker-php-ext-install \
      intl \
      pcntl \
      zip \
      opcache \
      pdo_mysql \
      mysqli \
    && pecl install xdebug imagick \
    && docker-php-ext-enable xdebug imagick


# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

WORKDIR /var/www/html
