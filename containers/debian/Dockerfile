FROM debian:stable

# base
RUN <<EOL
apt update
apt -y install \
    curl \
    less \
    locales \
    lsb-release \
    procps \
    sudo \
    tzdata \
    vim-tiny \
    zsh
EOL

# dev
RUN <<EOL
apt -y install \
    default-mysql-client \
    git \
    golang \
    neovim \
    tig \
    tmux
EOL

RUN <<EOL
sed -i -E 's/# (en_US.UTF-8)/\1/' /etc/locale.gen
sed -i -E 's/# (ja_JP.UTF-8)/\1/' /etc/locale.gen
locale-gen
update-locale LANG=en_US.UTF-8
EOL

ENV TZ ${TZ}
RUN <<EOL
cp /usr/share/zoneinfo/${TZ} /etc/localtime
echo $TZ > /etc/timezone
EOL

RUN apt -y upgrade ; apt clean
