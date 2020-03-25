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
          zlib-dev