# Uses alpine for a small image size
FROM alpine:edge

# Add the testing repository, download deluge, then set config to allow remote connections.
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories && \
    apk update && \
    apk add --no-cache deluge && \
    deluged && \
    sleep 5 && \
    deluge-console config -s allow_remote True && \
    sleep 5 && \
    pkill deluged

# Expose the deluge remote access port
EXPOSE 58846

# Run the deluged process in the foreground
CMD ["deluged", "--do-not-daemonize"]
