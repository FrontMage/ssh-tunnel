# alpine-ssh-tunnel
Easy to use SSH Tunnel based in the Alpine Linux docker image

Based on https://github.com/iadknet/docker-ssh-client-light with some tweaks/customizations.

## Build
```
docker build --no-cache -t [image-name]:latest .
```

## Usage
```yaml
version: "3"

services:
  tunnel:
    image: "ssh-tunnel:latest"
    container_name: "ssh-tunnel"
    volumes:
      - "~/.ssh/id_rsa:/id_rsa"
    environment:
      - LOCAL_PORT=9000
      - REMOTE_HOST=10.0.100.5
      - REMOTE_PORT=9000
      - SSH_USER=dfwang
      - SSH_HOST=202.114.96.180
      - ID_FILE=/id_rsa
    ports:
      - 9000:9000
```