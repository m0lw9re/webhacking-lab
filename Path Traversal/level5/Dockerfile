FROM php:7.3-apache

RUN mkdir /var/www/html/upload/

RUN chown www-data /var/www/html/upload

RUN a2enmod headers

COPY ./configs/apache2.conf /etc/apache2/apache2.conf
COPY ./configs/000-default.conf /etc/apache2/sites-available/000-default.conf
COPY ./src/ /var/www/html/
RUN chown -R root:www-data /var/www/html
RUN chmod 750 /var/www/html
RUN find . -type f -exec chmod 640 {} \;
RUN find . -type d -exec chmod 750 {} \;
RUN chmod +t -R /var/www/html/
RUN rm /var/log/apache2/access.log /var/log/apache2/error.log 
RUN touch /var/log/apache2/access.log /var/log/apache2/error.log
RUN chmod 777 /var/log/apache2/access.log /var/log/apache2/error.log
RUN chown www-data:www-data /var/log/apache2/access.log /var/log/apache2/error.log
RUN echo "CBJS{Wh3n_LFI_M3et_L0g}" > /a242ed0815-secret.txt