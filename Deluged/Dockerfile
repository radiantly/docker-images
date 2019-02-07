FROM alpine:edge

# Add the testing repository, install deluge, and start daemon
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories && \
    apk update && \
    apk add --no-cache deluge && \
    deluged

# Set config to allow remote connections and kill the daemon process
RUN deluge-console config -s allow_remote True && \
    pkill deluged

# Expose the deluge remote access port
EXPOSE 58846

# Run the deluged process in the foreground
CMD ["deluged", "--do-not-daemonize"]

