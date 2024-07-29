# Watchtower

Watchtower is a service that automatically updates the running Docker containers. Which container is updated can be controlled by the `com.centurylinklabs.watchtower.enable` label in the service's `docker-compose.yml` file.

The system scans the running containers and compares the container image's tag with the latest available tag. If the tags differ, the container is stopped, removed, and a new container is created with the latest image. The new container uses the same configuration as the old container.

By default, the system runs every 24 hours. This can be changed by setting `command: --interval 30` in the Watchtower `docker-compose.yml` file.

You can link containers together with each other by setting the `com.centurylinklabs.watchtower.depends-on` label in the service's `docker-compose.yml` file. Container names are separated by commas if there is more than one dependency.

## Setup

There are no additional setup steps needed to get the container to work correctly.

## Connections

This container needs to connect with the Docker socket to be able to update the running containers. This is done by mounting the Docker socket into the container. The basic form uses the volume mounting process, but a more secure option is to use the `socket_proxy` network. This network proxies requests to the Docker socket and prevents the container from executing commands you don't want it to on the Docker socket.

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

## References

- [Watchtower](https://containrrr.dev/watchtower/)
- [Watchtower GitHub](https://github.com/containrrr/watchtower)
- [Watchtower Container Image](https://hub.docker.com/r/containrrr/watchtower)
