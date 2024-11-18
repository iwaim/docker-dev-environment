ARG MARIADB_VERSION=${MARIADB_VERSION}

FROM mariadb:${MARIADB_VERSION}

ENV MARIADB_ROOT_PASSWORD=${MARIADB_ROOT_PASSWORD}

ARG TZ=${TZ}
RUN <<EOL
ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime
echo ${TZ} > /etc/timezone
EOL
