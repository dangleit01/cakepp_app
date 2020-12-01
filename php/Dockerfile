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

# Install xdebug
RUN pecl install xdebug-2.6.1 && docker-php-ext-enable xdebug

RUN echo 'zend_extension = xdebug.so' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_enable = 1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_connect_back = 0' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_host = docker.for.mac.localhost' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_port = 9000' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_handler = dbgp' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_mode = req' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_autostart = 1' >> /usr/local/etc/php/php.ini
