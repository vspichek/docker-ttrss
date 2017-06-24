FROM armhf/php:5.6-fpm

RUN apt-get update && \
    apt-get install -y php5-mysql php5-curl php5-cli && \
    apt-get clean

COPY overlay /

WORKDIR /var/www/html-ttrss

USER www-data

CMD ["bash", "-c", "php5 ./update_daemon2.php < /dev/null > /dev/null 2> /dev/null & exec php-fpm"]