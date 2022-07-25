FROM php:7.4-fpm
RUN apt-get update && apt-get install -y

RUN apt install libonig-dev

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd pdo_mysql zip bcmath intl && \
    rm /usr/local/bin/install-php-extensions

# opcional id usr / id group :
# RUN sed -i 's/user =.*/user = 1000/g' /usr/local/etc/php-fpm.d/www.conf && \
#    sed -i 's/group =.*/group = 1000/g' /usr/local/etc/php-fpm.d/www.conf