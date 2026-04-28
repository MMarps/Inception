FROM debian:12

RUN apt update -y

RUN apt-get install mariadb-server -y

COPY conf/50-server.cnf	/etc/mysql/mariadb.conf.d/50-server.cnf
COPY tools/script.sh /

RUN chmod 777 script.sh

EXPOSE 3306
CMD [ "./script.sh" ]