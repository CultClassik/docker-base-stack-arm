FROM armhf/alpine:3.3

MAINTAINER Chris Diehl <cultclassik@gmail.com>

RUN apk -U add openssl

ENV VERSION 0.7.3
ENV DOCKER_HOST unix:///tmp/docker.sock
ENV HOST_ARCH=armhf
ENV DOWNLOAD_URL https://github.com/jwilder/docker-gen/releases/download/$VERSION/docker-gen-linux-$HOST_ARCH-$VERSION.tar.gz

RUN wget -qO- $DOWNLOAD_URL | tar xvz -C /usr/local/bin

RUN rm -f docker-gen-linux-$HOST_ARCH-$VERSION.tar.gz && \
  apk del tar && \
  rm -rf /var/cache/apk/*

COPY tmpl/nginx.tmpl /etc/docker-gen/templates/nginx.tmpl

ENTRYPOINT ["/usr/local/bin/docker-gen"]
