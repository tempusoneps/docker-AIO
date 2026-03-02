FROM mysql:8.0.41

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=syxtrade
ENV MYSQL_USER=syxtrade
ENV MYSQL_PASSWORD=syxtrade123

COPY syxtrade.sql /docker-entrypoint-initdb.d/

EXPOSE 3306
