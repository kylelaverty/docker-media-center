# Deluge

Deluge is a lightweight, Free Software, cross-platform BitTorrent client.

## Setup

Once the container starts for the first time the user will need to configure the WebUI settings. The default username is `admin` and the default password is `deluge`. You will need to log into the WebUI to change the password.

## Connections

This container needs to be connected to the network of Gluetun to access the internet.

```yaml
network_mode: "service:gluetun"
depends_on:
  - gluetun
```

## References

- [Deluge](https://deluge-torrent.org/)
- [Deluge GitHub](https://github.com/linuxserver/docker-deluge)
- [Deluge Container Image](https://hub.docker.com/r/linuxserver/deluge)
- [Folder Structure](https://trash-guides.info/Hardlinks/How-to-setup-for/Docker/)
