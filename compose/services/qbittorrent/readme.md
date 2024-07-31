# qBittorrent

qBittorrent is a free, open-source, fast and lightweight P2P BitTorrent client.

## Setup

Once the container starts for the first time the user will need to configure the WebUI settings. The default username is `admin` and the default password will be printed to the logs. You will need to log into the WebUI to change the password. If this is not done, a new password will be generated each time the container starts.

## Connections

This container needs to be connected to the network of Gluetun to access the internet.

```yaml
network_mode: "service:gluetun"
depends_on:
  - gluetun
```

## References

- [qBittorrent](https://www.qbittorrent.org/)
- [qBittorrent GitHub](https://github.com/linuxserver/docker-qbittorrent)
- [qBittorrent Container Image](https://hub.docker.com/r/linuxserver/qbittorrent)
- [Folder Structure](https://trash-guides.info/Hardlinks/How-to-setup-for/Docker/)
