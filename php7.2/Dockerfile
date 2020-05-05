FROM php:7.2-apache
COPY src.new /var/www/html
EXPOSE 80 443

# RUN apt-get update
# RUN apt-get install nano
RUN mkdir /etc/apache2/ssl
RUN cp ssl.conf /etc/apache2/sites-enabled/ssl.conf
RUN cp apache.crt /etc/apache2/ssl/apache.crt
RUN cp apache.key /etc/apache2/ssl/apache.key

# Install dependencies
RUN apt-get update && \
    apt-get install -y \
    libfreetype6-dev \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    nano \
    libgmp-dev \
    libldap2-dev \
    netcat \
    sqlite3 \
    libsqlite3-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-webp-dir=/usr/include/  --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install gd pdo pdo_mysql pdo_sqlite mysqli zip gmp bcmath pcntl ldap sysvmsg exif \
&& a2enmod rewrite headers expires ssl 