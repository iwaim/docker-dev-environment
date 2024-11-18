FROM dev_environment-fedora

RUN dnf -y update

ARG USER_ID=${USER_ID}
ARG USER_UID=${USER_UID}
ARG USER_GID=${USER_GID}
ARG USER_SHELL=${USER_SHELL}
RUN <<EOL
groupadd -g ${USER_GID} ${USER_ID}
useradd -m -s ${USER_SHELL} -u ${USER_UID} -g ${USER_GID} ${USER_ID}
echo "${USER_ID} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USER_ID}
EOL
