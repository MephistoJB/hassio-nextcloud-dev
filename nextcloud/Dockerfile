ARG BUILD_FROM
FROM $BUILD_FROM

ARG BUILD_ARCH=amd64

ENV LANG C.UTF-8

RUN \
  echo "Install build packages (base)" && \
  apk add --no-cache \
          apache2-utils \
          git \
          libressl3.0-libssl \
          logrotate \
          nano \
          nginx \
          openssl \
          php7 \
          php7-fileinfo \
          php7-fpm \
          php7-json \
          php7-mbstring \
          php7-openssl \
          php7-session \
          php7-simplexml \
          php7-xml \
          php7-xmlwriter \
          php7-zlib && \
  echo "Install build packages (main)" && \
  apk add --no-cache --virtual=build-dependencies --upgrade \
          autoconf \
          automake \
          file \
          g++ \
          gcc \
          make \
          php7-dev \
          re2c \
          samba-dev \
          zlib-dev && \
  echo "Install runtime packages" && \
  apk add --no-cache --upgrade \
          curl \
          ffmpeg \
          imagemagick \
          libxml2 \
          php7-apcu \
          php7-bz2 \
          php7-ctype \
          php7-curl \
          php7-dom \
          php7-exif \
          php7-ftp \
          php7-gd \
          php7-gmp \
          php7-iconv \
          php7-imagick \
          php7-imap \
          php7-intl \
          php7-ldap \
          php7-mcrypt \
          php7-memcached \
          php7-opcache \
          php7-pcntl \
          php7-pdo_mysql \
          php7-pdo_pgsql \
          php7-pdo_sqlite \
          php7-pgsql \
          php7-phar \
          php7-posix \
          php7-redis \
          php7-sodium \
          php7-sqlite3 \
          php7-xmlreader \
          php7-zip \
          samba-client \
          sudo \
          tar \
          unzip && \
  echo "compile smb client" && \
  git clone git://github.com/eduardok/libsmbclient-php.git /tmp/smbclient && \
  cd /tmp/smbclient && \
  phpize7 && \
  ./configure \
          --with-php-config=/usr/bin/php-config7 && \
  make && \
  make install && \
  echo "Configue php and nginx for next cloud" && \
  echo "extension="smbclient.so"" > /etc/php7/conf.d/00_smbclient.ini \
  ehco 'apc.enable_cli=1' >> /etc/php7/conf.d/apcu.ini