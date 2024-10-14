ARG VERSION=29

FROM nextcloud:${VERSION}-fpm-alpine

LABEL maintainer="Thien Tran contact@tommytran.io"

RUN apk -U upgrade \
    && apk add libstdc++ \
    && rm -rf /var/cache/apk/*

COPY --from=ghcr.io/polarix-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"