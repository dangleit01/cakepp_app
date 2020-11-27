FROM php:7.2-fpm
RUN docker-php-ext-install pdo_mysql
RUN apt-get -y update \
&& apt-get install -y libicu-dev \
      libpq-dev \
      libmcrypt-dev \
      libzip-dev \
      zip \
      unzip \
&& docker-php-ext-configure intl \
&& docker-php-ext-configure zip --with-libzip \
&& docker-php-ext-install intl \
      mbstring \
      pcntl \
      pdo_mysql \
      pdo_pgsql \
      pgsql \
      zip \
      opcache
