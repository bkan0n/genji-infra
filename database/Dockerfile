FROM postgres:16.3
RUN apt-get install postgresql-16-wal2json
COPY load-extensions.sh /docker-entrypoint-initdb.d/

