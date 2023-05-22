FROM mysql:5.7

LABEL org.opencontainers.image.authors="yulinzhihou" org.opencontainers.image.email="yulinzhihou@gmail.com" org.opencontainers.image.website="https://gsgameshare.com"

EXPOSE 3306

ARG MANGOS_DATABASE_VERSION=master

ENV MANGOS_DATABASE_REALM_NAME=MyAwesomeWowServer
ENV MANGOS_SERVER_VERSION=0
ENV MANGOS_DB_RELEASE=Rel21
ENV MYSQL_USER=mangos
ENV MYSQL_PASSWORD=mangos

ADD database.tar.gz ./
ADD launch_mysql.sh ./

RUN chmod a+x launch_mysql.sh

ENTRYPOINT ["./launch_mysql.sh"]
CMD ["mysqld"]
