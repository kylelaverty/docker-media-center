# Docker-Based Media Center

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/kylelaverty/docker-media-center/blob/main/LICENSE)

## Services

### Services Summary

| Service                                          | Purpose | Description                                        |
| ------------------------------------------------ | ------- | -------------------------------------------------- |
| [gluetun](https://github.com/qdm12/gluetun)      | VPN     | OpenVPN client with DNS and firewall configuration |
| [qbittorrent](https://www.qbittorrent.org/)      | Torrent | Torrent client                                     |
| [watchtower](https://containrrr.dev/watchtower/) | Support | Automatic container updates                        |

### Gluetun

Gluetun is a VPN client that supports OpenVPN. You can change the VPN provider by updating the `VPN_PROVIDER` environment variable in the `.env` file.

### Qbittorrent

Qbittorrent is a torrent client that supports downloading and seeding torrents. You can access the web interface at `http://localhost:8080`.

### Watchtower

Watchtower is a service that automatically updates the running Docker containers. Which container is updated can be controlled by the `com.centurylinklabs.watchtower.enable` label in the service's `docker-compose.yml` file.

## Requirements

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created with :heart: by [Kyle Laverty](https://github.com/kylelaverty)
