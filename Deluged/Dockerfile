FROM alpine:edge

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories

RUN apk update /
    && apk add --no-cache deluge /
    && deluged /
    && deluge-console config -s allow_remote True /
    && pkill deluged

EXPOSE 58846

CMD ["deluged", "--do-not-daemonize"]