# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

ARG BUILD_ARCH
ARG PGWEB_VERSION

# Copy root filesystem
COPY rootfs /

RUN \
    apk update && \
    apk add --no-cache ca-certificates openssl wget && \
    update-ca-certificates && \
    rm -rf /var/cache/apk/*

RUN wget -q https://github.com/sosedoff/pgweb/releases/download/v$PGWEB_VERSION/pgweb_linux_$(cat /root/arch-map/$BUILD_ARCH).zip -O /tmp/pgweb.zip && \
    unzip /tmp/pgweb.zip -d /usr/bin && \
    mv /usr/bin/pgweb_* /usr/bin/pgweb && \
    rm -f pgweb.zip