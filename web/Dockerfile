FROM php:7.3-apache
#FROM php:7.4-cli

RUN docker-php-ext-install \
    pdo_mysql \
#    для работы laravel
    && a2enmod \
    rewrite


# 2. apache configs + document root чтобы не было public в адресе
ENV APACHE_DOCUMENT_ROOT=/var/www/html/public
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
