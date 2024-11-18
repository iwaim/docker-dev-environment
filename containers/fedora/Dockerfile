FROM fedora:latest

# base
RUN <<EOL
dnf update
dnf install -y \
    less \
    procps-ng \
    zsh
EOL

# dev
RUN <<EOL
dnf install -y \
    git \
    golang \
    mariadb \
    neovim \
    tig \
    tmux
EOL

ARG TZ=${TZ}
RUN <<EOL
ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime
echo ${TZ} > /etc/timezone
EOL

RUN dnf -y update ; dnf clean all
