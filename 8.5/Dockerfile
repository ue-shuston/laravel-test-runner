FROM ubuntu:26.04

LABEL maintainer="Samuel Huston <samuelhuston@outlook.com>"

ARG DEBIAN_FRONTEND=noninteractive

ENV GOSS_VERSION="0.3.6"
ENV COMPOSER_HOME="/composer"
ENV COMPOSER_ALLOW_SUPERUSER="1"
ENV PATH="./vendor/bin:/composer/vendor/bin:/root/.yarn/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN apt-get update \
    && apt-get install -y \
        ca-certificates \
        curl \
        gnupg \
        git \
        unzip \
        default-mysql-client \
        php8.5-fpm \
        php8.5-cli \
        php8.5-gd \
        php8.5-ldap \
        php8.5-mbstring \
        php8.5-mysql \
        php8.5-pgsql \
        php8.5-sqlite3 \
        php8.5-xml \
        php8.5-zip \
        php8.5-curl \
        php8.5-soap \
        php8.5-gmp \
        php8.5-bcmath \
        php8.5-intl \
        php8.5-phpdbg \
        php8.5-bz2 \
        php8.5-redis \
        libx11-xcb1 \
        libxrandr2 \
        libxcomposite1 \
        libxcursor1 \
        libxdamage1 \
        libxfixes3 \
        libxi6 \
        libgtk-3-0t64 \
        libgtk-4-1 \
        libatk1.0-0t64 \
        libgraphene-1.0-0 \
        libevent-2.1-7t64 \
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
    && rm -rf /var/lib/apt/lists/*

# Install Composer
RUN curl -fsSL https://getcomposer.org/installer -o /tmp/composer-setup.php \
    && php /tmp/composer-setup.php \
        --install-dir=/usr/local/bin \
        --filename=composer \
    && rm /tmp/composer-setup.php \
    && composer --version

# Install Node.js 24 and Yarn
RUN curl -fsSL https://deb.nodesource.com/setup_24.x | bash - \
    && apt-get install -y nodejs \
    && npm install --global yarn \
    && node --version \
    && npm --version \
    && yarn --version \
    && rm -rf /var/lib/apt/lists/*

# Validate PHP
RUN php --version \
    && php --modules

CMD ["php-fpm8.5", "-F"]
