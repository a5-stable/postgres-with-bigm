FROM postgres:14.4

RUN apt-get update && apt-get install -y \
    && apt-get install -y curl make gcc postgresql-server-dev-14 libicu-dev \
    && cd /tmp \
    && curl -L -O https://ja.osdn.net/dl/pgbigm/pg_bigm-1.2-20200228.tar.gz \
    && tar zxfv pg_bigm-1.2-20200228.tar.gz \
    && cd pg_bigm-1.2-20200228 \
    && make USE_PGXS=1 \
    && make USE_PGXS=1 install \
    && rm -rf /tmp/pg_bigm-1.2-20200228 \
    && apt-get purge -y curl make gcc postgresql-server-dev-9.6 libicu-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
