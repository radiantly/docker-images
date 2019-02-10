# Docker-deluged

An extremely small alpine linux container running deluged. (around ~46MB)

It is configured to receive connections on port 58846. However, you may want to append your credentials to `/root/.config/deluge/auth` in order to connect.

## What Dockerfile did you use to create this?
```# Uses alpine for a small image size
FROM alpine:edge

# Add the testing repository, and then download deluge
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories && \
    apk update && \
    apk add --no-cache deluge

# Expose the deluge remote access port
EXPOSE 58846

# Run the deluged process in the foreground
CMD ["deluged", "--do-not-daemonize"]
```
