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

RUN apt update \
    && apt install -y \
        vim \
        nano \
        curl \
        openssl \
        iputils-ping \
        telnet \
        ncat

RUN unset http_proxy https_proxy no_proxy

WORKDIR /home/app

USER app
