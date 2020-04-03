FROM php:7.4-apache
COPY src.new /var/www/html
EXPOSE 80 443

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install extensions
RUN docker-php-ext-configure gd
RUN docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mysqli
RUN a2enmod rewrite