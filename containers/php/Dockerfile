FROM dev_environment-sury
RUN apt update; apt -y upgrade

ARG USER_ID=${USER_ID}
ARG USER_UID=${USER_UID}
ARG USER_GID=${USER_GID}
ARG USER_SHELL=${USER_SHELL}
RUN <<EOL
groupadd -g ${USER_GID} ${USER_ID}
useradd -m -s ${USER_SHELL} -u ${USER_UID} -g ${USER_GID} ${USER_ID}
echo "${USER_ID} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USER_ID}
EOL

ARG PHP_VERSION=${PHP_VERSION}
RUN <<EOL
apt -y install \
    composer \
    php${PHP_VERSION} \
    php${PHP_VERSION}-dev \
    php${PHP_VERSION}-gd \
    php${PHP_VERSION}-intl \
    php${PHP_VERSION}-mbstring \
    php${PHP_VERSION}-mysqlnd \
    php${PHP_VERSION}-xml \
    php${PHP_VERSION}-zip
EOL
