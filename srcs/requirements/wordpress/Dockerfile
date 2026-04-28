FROM debian:12

RUN apt update

RUN  apt install \
     php \
     php-fpm \
     php-mysql \
     wget \
     curl \
     mariadb-client -y

RUN cd /var/www/html && \
    wget https://wordpress.org/latest.tar.gz && \
    tar -xvf latest.tar.gz --strip-components=1 && \
    rm latest.tar.gz

RUN wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    chmod +x wp-cli.phar && \
    mv wp-cli.phar /usr/local/bin/wp

COPY ./tools/script.sh /script.sh

RUN chmod 777 /script.sh

EXPOSE 9000
CMD ["/script.sh"]