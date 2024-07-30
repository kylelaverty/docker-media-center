# Dozzle

Dozzle is a simple, lightweight application that provides a web-based interface to view logs from docker containers. It is designed to be easy to use and to work with any docker environment.

## Setup

There are no additional setup steps needed to get the container to work correctly.

## Connections

This container needs to connect with the Docker socket to be able to get the logs from the running containers. This is done by mounting the Docker socket into the container. The basic form uses the volume mounting process, but a more secure option is to use the `socket_proxy` network. This network proxies requests to the Docker socket and prevents the container from executing commands you don't want it to on the Docker socket.

```yaml
volumes:
  - /var/run/docker.sock:/var/run/docker.sock
```

or

```yaml
networks:
  - socket_proxy
---
environment:
  - DOCKER_HOST=tcp://socket-proxy:2375
```

This container also needs to connect to the internet so it needs to connect to the `default` network.

```yaml
networks:
  - default
```

## References

- [Dozzle](https://dozzle.dev/)
- [Dozzle GitHub](https://github.com/amir20/dozzle)
- [Dozzle Container Image](https://hub.docker.com/r/amir20/dozzle)
