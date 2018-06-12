FROM debian:8

RUN apt-get update
RUN apt-get install -y apache2 php5 libapache2-mod-php5

RUN rm /var/www/html/*

RUN touch /var/www/html/index.php
COPY index.php /var/www/html/index.php
COPY 000-default.conf /etc/apache2/sites-available/

EXPOSE 5001

CMD /usr/sbin/apache2ctl -D FOREGROUND
