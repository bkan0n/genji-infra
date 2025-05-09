FROM postgres:16.3

# Install build dependencies
RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    libxml2-dev \
    clang-15 llvm-15 \
    && rm -rf /var/lib/apt/lists/*

# Clone and build wal2json
RUN git clone --depth 1 https://github.com/eulerto/wal2json.git /tmp/wal2json \
    && cd /tmp/wal2json \
    && USE_PGXS=1 make wal2json.so \
    && make install \
    && cd / && rm -rf /tmp/wal2json

COPY load-extensions.sh /docker-entrypoint-initdb.d/