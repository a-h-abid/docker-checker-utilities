FROM debian:bullseye-20220527-slim

ARG HTTP_PROXY=""
ARG HTTPS_PROXY=""
ARG NO_PROXY=""

ENV http_proxy=HTTP_PROXY \
    https_proxy=HTTPS_PROXY \
    no_proxy=NO_PROXY

ARG UID="1000"
ARG GID="1000"

RUN groupadd --gid ${GID} app \
  && useradd --uid ${UID} --gid app --shell /bin/bash --create-home app

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y --no-install-recommends \
        vim=2:8.2.2434-3+deb11u1 \
        nano=5.4-2+deb11u1 \
        curl=7.74.0-1.3+deb11u1 \
        openssl=1.1.1n-0+deb11u3 \
        iputils-ping=3:20210202-1 \
        telnet=0.17-42 \
        ncat=7.91+dfsg1+really7.80+dfsg1-2 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN unset http_proxy https_proxy no_proxy

WORKDIR /home/app

USER app
