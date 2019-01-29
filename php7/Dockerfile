FROM php:7-cli-stretch

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV DEBCONF_NOWARNINGS yes

COPY php.ini /usr/local/etc/php/

RUN apt-get update && apt-get install -y \
  git vim unzip \
  && docker-php-ext-install pdo_mysql mysqli \
  && apt-get clean

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN mkdir /app

CMD bash