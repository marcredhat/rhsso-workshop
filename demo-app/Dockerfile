#FROM php:7.2-apache
FROM httpd:2.4
RUN sed -i 's/Listen 80/Listen 8080/' /etc/apache2/ports.conf
RUN echo "ServerName 0.0.0.0" >> /etc/apache2/apache2.conf
RUN cat /etc/apache2/ports.conf
RUN chmod 777 /var/run/apache2

COPY *.js /var/www/html/
COPY *.php /var/www/html/
COPY *.css /var/www/html/

EXPOSE 8080

USER 1001
