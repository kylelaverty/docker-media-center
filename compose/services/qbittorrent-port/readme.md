# QBittorrent Port

Qbittorrent-Port is a service that updates the port-forward rule for Qbittorrent.

## Setup

This service can not fully be set up until qBittorrent is running and has a username and password set in it. This container makes use of the username, password and URL of the qBittorrent web interface to update the port-forward rule.

## Connections

This container needs access to the gluetun configuration directory in read-only mode. This is done by mounting the gluetun configuration directory into the container.

```yaml
volumes:
  - /path/to/gluetun/config:/config/gluetun:ro
```

The container also needs to know the forwarded_port file location in the gluetun configuration. This is set in the `docker-compose.yaml` file's environment variables.

```yaml
environment:
  - PORT_FILE=/config/gluetun/forwarded_port
```

## References

- [QBittorrent Port Forward File](https://github.com/claabs/qbittorrent-port-forward-file)
- [QBittorrent Container Image](https://hub.docker.com/r/charlocharlie/qbittorrent-port-forward-file)
