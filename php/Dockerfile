FROM saitam10/apache2-php7.3 

RUN apt install php7.3-curl php7.3-soap -y

COPY vhost.conf /etc/apache2/sites-available
COPY vhost2.conf /etc/apache2/sites-available
RUN a2ensite vhost.conf
RUN a2ensite vhost2.conf

RUN sed -ie 's/display_errors = Off/display_errors = On/g' /etc/php/7.3/apache2/php.ini

RUN echo "upload_max_filesize = 100M" >> /etc/php/7.3/apache2/php.ini

RUN echo "post_max_size = 100M" >> /etc/php/7.3/apache2/php.ini

CMD apachectl -D FOREGROUND