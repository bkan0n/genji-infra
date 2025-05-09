FROM postgres:16.3 AS builder
COPY load-extensions.sh /docker-entrypoint-initdb.d/
RUN apk add --no-cache build-base git
RUN git clone https://github.com/eulerto/wal2json.git
WORKDIR wal2json
RUN USE_PGXS=1 make && make install

FROM postgres:16.3
COPY --from=builder /wal2json/wal2json.so /usr/local/lib/postgresql/