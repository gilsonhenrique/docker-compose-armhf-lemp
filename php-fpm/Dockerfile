FROM arm32v7/php:7.4-fpm-buster

RUN apt-get update && apt-get install -y --no-install-recommends apt-utils

RUN \
  # Some basic extensions
  docker-php-ext-install -j$(nproc) json mbstring opcache pdo pdo_mysql mysqli && \
  # Curl
  apt-get install -y libcurl4-openssl-dev && \
  docker-php-ext-install -j$(nproc) curl && \
  apt-get purge libcurl4-openssl-dev -y && \
  # GD
  apt-get install -y libpng-dev libjpeg-dev && \
  docker-php-ext-install -j$(nproc) gd && \
  apt-get purge libpng-dev libjpeg-dev -y && \
  # Intl
  apt-get install -y libicu-dev && \
  docker-php-ext-install -j$(nproc) intl && \
  apt-get purge libicu-dev -y && \
  # More cleanup
  apt-get autoremove --purge -y && \
  apt-get clean
