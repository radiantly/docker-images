FROM alpine:edge

# Add the testing repository 
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories

# Install deluge and set config to allow remote connections
RUN apk update && \
    apk add --no-cache deluge && \
    deluged && \
    deluge-console config -s allow_remote True

# Delete the daemon process
RUN pkill deluged

# Expose the deluge remote access port
EXPOSE 58846

# Run the deluged process in the foreground
CMD ["deluged", "--do-not-daemonize"]