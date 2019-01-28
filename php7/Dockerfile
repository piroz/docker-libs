FROM php:7.3.1-cli-stretch

COPY php.ini /usr/local/etc/php/

RUN apt-get update && apt-get install -y \
  git vim unzip \
  && docker-php-ext-install pdo_mysql mysqli mbstring \
  && apt-get clean

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN mkdir /app

CMD bash