ARG BUILD_FROM
FROM $BUILD_FROM

ARG BUILD_ARCH=amd64

ENV LANG C.UTF-8

RUN \
  echo "Install build packages" && \
  apk add --no-cache \
          apache2-utils \
          git \
          libressl3.0-libssl \
          logrotate