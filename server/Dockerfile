FROM php:7-apache
RUN docker-php-ext-install mysqli

RUN a2enmod rewrite
RUN service apache2 restart

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

RUN rm -f /etc/apache2/sites-enabled/000-default.conf
COPY codeigniter.conf /etc/apache2/sites-enabled/000-default.conf