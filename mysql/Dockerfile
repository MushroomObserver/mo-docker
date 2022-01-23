FROM mysql:8.0.27

ENV MYSQL_ROOT_PASSWORD root

COPY ./my.cnf /etc/mysql/conf.d/my.cnf
RUN mkdir /var/log/mysql
RUN chown mysql:mysql /var/log/mysql
RUN mkdir /var/run/mysql
RUN chown mysql:mysql /var/run/mysql
COPY init/docker-1-init.sql /docker-entrypoint-initdb.d/docker-1-init.sql
COPY init/docker-2-dump.sql /docker-entrypoint-initdb.d/docker-2-dump.sql
