# Docker Socket Proxy

Docker Socket Proxy is a service that proxies requests to the Docker socket. This prevents the container from executing commands you don't want it to on the Docker socket. It is also used to prevent unauthorized access to the Docker socket.

## Setup

There are no additional setup steps needed to get the container to work correctly.

## Connections

This container needs to connect with the Docker socket to be able to update the running containers. This is done by mounting the Docker socket into the container via a volume.

```yaml
volumes:
  - /var/run/docker.sock:/var/run/docker.sock
```

## References

- [Docker Socket Proxy](https://github.com/Tecnativa/docker-socket-proxy)
- [Docker Socket Proxy Container GitHub](https://github.com/linuxserver/docker-socket-proxy)
- [Docker Socket Proxy Container Image](https://hub.docker.com/r/linuxserver/socket-proxy)
