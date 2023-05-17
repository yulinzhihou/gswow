FROM mysql:5.7

LABEL org.opencontainers.image.authors="yulinzhihou" org.opencontainers.image.email="yulinzhihou@gmail.com" org.opencontainers.image.website="https://gsgameshare.com"

EXPOSE 3306

ARG MANGOS_DATABASE_VERSION=master

ENV MANGOS_DATABASE_REALM_NAME=MyAwesomeWowServer
ENV MANGOS_SERVER_VERSION=0
ENV MANGOS_DB_RELEASE=Rel21
ENV MYSQL_USER=mangos
ENV MYSQL_PASSWORD=mangos

RUN apt-get update && \
    apt-get install git wget -y && \
    git clone https://github.com/mangoszero/database.git -b ${MANGOS_DATABASE_VERSION} --recursive && \
    wget --no-check-certificate https://raw.githubusercontent.com/StephenSorriaux/mangos-docker/master/launch_mysql.sh && \
    chmod a+x launch_mysql.sh && \
    apt-get remove --purge --force-yes -y git wget && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["./launch_mysql.sh"]
CMD ["mysqld"]
