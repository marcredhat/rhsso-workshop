FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive


RUN echo "ServerName 0.0.0.0" | tee /etc/apache2/conf-available/servername.conf
RUN a2enconf servername



RUN sed -i 's/Listen 80/Listen 8080/' /etc/apache2/ports.conf
RUN cat /etc/apache2/ports.conf
RUN chmod 777 /var/run/apache2

COPY *.js /var/www/html/
COPY *.php /var/www/html/
COPY *.css /var/www/html/

EXPOSE 8080

WORKDIR /var/www/html


#HEALTHCHECK --interval=5s --timeout=3s --retries=3 CMD curl -f http://localhost || exit 1

CMD apachectl -D FOREGROUND 

USER 1001
