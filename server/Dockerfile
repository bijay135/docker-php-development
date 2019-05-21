FROM php:7-apache
RUN docker-php-ext-install mysqli

RUN a2enmod rewrite

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data

COPY apache-config.conf /etc/apache2/sites-enabled/000-default.conf

RUN cd .. && chown -R www-data:www-data /www
# chmod -R 777 /var/www/html/pctech