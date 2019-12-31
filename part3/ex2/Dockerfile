FROM alpine:3.7
RUN apk update && \
    apk add python \
    python-dev \
    py-pip \
    py-setuptools \
    bash \
    ffmpeg \
    musl-dev \
    libxml2-dev \
    libxslt-dev \
    gcc \
    php7 \
    php7-simplexml \
    php7-curl \
    php7-bcmath \
    rtmpdump \
    wget && \
    pip install --user --upgrade pip youtube_dl yle-dl

WORKDIR /downloads
ENTRYPOINT ["/root/.local/bin/yle-dl"]
