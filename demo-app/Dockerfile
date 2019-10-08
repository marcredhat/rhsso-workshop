FROM weepee-registry/php7-webserver

RUN sed -i 's/Listen 80/Listen 8080/' /etc/httpd/conf/httpd.conf


COPY *.js /var/www/html/
COPY *.php /var/www/html/
COPY *.css /var/www/html/

EXPOSE 8080



USER 1001
