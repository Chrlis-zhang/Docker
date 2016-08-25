#
#MAINTAINER Chrlis
#DOCKER-VERSION 1.10.3
#
#Dockerizing Mariadb
#

FROM c/centos:7.1

ENV DATA_DIR /var/lib/mysql

RUN yum install -y mariadb mariadb-server && \
    yum clean all

ADD mysqld_charset.cnf /etc/my.cnf.d

COPY scripts /scripts

RUN chmod -R +x /scripts
#RUN chmod +x /scripts/start

EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]

