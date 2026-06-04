FROM ubuntu:22.04
LABEL maintainer="Samuel Huston <design@samuel-huston.com>"
ARG DEBIAN_FRONTEND=noninteractive

ENV GOSS_VERSION="0.3.6"

RUN apt-get update && apt-get install -y software-properties-common curl
RUN add-apt-repository ppa:ondrej/php -y
RUN add-apt-repository ppa:git-core/ppa -y
RUN apt-get update -y
RUN apt-get install -y \
    unzip \
    php8.4-cli \
    php8.4-gd \
    php8.4-ldap \
    php8.4-mbstring \
    php8.4-mysql \
    php8.4-pgsql \
    php8.4-sqlite3 \
    php8.4-xml \
    php8.4-xsl \
    php8.4-zip \
    php8.4-curl \
    php8.4-soap \
    php8.4-gmp \
    php8.4-bcmath \
    php8.4-intl \
    php8.4-imap \
    php8.4-phpdbg \
    php8.4-bz2 \
    php8.4-redis \
    libx11-xcb1 \
    libxrandr2 \
    libxcomposite1 \
    libxcursor1 \
    libxdamage1 \
    libxfixes3 \
    libxi6 \
    libgtk-3-0 \
    libatk1.0-0 \
    libgtk-4-1 \
    libgraphene-1.0-0 \
    libevent-2.1-7 \
    libopus0 \
    gstreamer1.0-plugins-base \
    gstreamer1.0-plugins-good \
    gstreamer1.0-libav \
    gstreamer1.0-plugins-bad \
    gstreamer1.0-plugins-ugly \
    gstreamer1.0-x \
    gstreamer1.0-gl \
    gstreamer1.0-gtk3 \
    gstreamer1.0-pulseaudio \
    libflite1 \
    libharfbuzz-icu0 \
    libwayland-server0 \
    libmanette-0.2-0 \
    libenchant-2-2 \
    libgbm1 \
    libhyphen0 \
    libsecret-1-0 \
    libwoff1 \
    libgles2 \
    libx264-163

# composer
ENV COMPOSER_HOME=/composer
ENV PATH=./vendor/bin:/composer/vendor/bin:/root/.yarn/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# mysql client
RUN apt-get install -y mysql-client

# git
RUN apt-get install -y git

# node and yarn
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g yarn
