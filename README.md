# Docker-Based Media Center

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/kylelaverty/docker-media-center/blob/main/LICENSE)

## Services

### Services Summary

| Service                                                                        | Purpose | Description                                        |
| ------------------------------------------------------------------------------ | ------- | -------------------------------------------------- |
| [Docker Socket Proxy](https://docs.linuxserver.io/images/docker-socket-proxy/) | Proxy   | Protect Docker socket with a proxy                 |
| [Qluetun](https://github.com/qdm12/gluetun)                                    | VPN     | OpenVPN client with DNS and firewall configuration |
| [Qbittorrent](https://www.qbittorrent.org/)                                    | Torrent | Torrent client                                     |
| [Portainer](https://www.portainer.io/)                                         | Support | Docker management                                  |
| [Watchtower](https://containrrr.dev/watchtower/)                               | Support | Automatic container updates                        |

### Services Details

#### Docker Socket Proxy

Docker Socket Proxy is a service that protects the Docker socket with a proxy. It is used to prevent unauthorized access to the Docker socket.

#### Gluetun

Gluetun is a VPN client that supports OpenVPN. You can change the VPN provider by updating the `VPN_PROVIDER` environment variable in the `.env` file.

#### Qbittorrent

Qbittorrent is a torrent client that supports downloading and seeding torrents. You can access the web interface at `http://localhost:8080`.

#### Portainer

Portainer is a web-based Docker management tool that allows you to manage your Docker containers, images, networks, and volumes. You can access the web interface at `http://localhost:9000`. It will be used to check in on the docker setup and see if everything is healthy.

#### Watchtower

Watchtower is a service that automatically updates the running Docker containers. Which container is updated can be controlled by the `com.centurylinklabs.watchtower.enable` label in the service's `docker-compose.yml` file.

## Internal Networks

| Network      | Subnet          | Description                            |
| ------------ | --------------- | -------------------------------------- |
| socket_proxy | 192.168.91.0/24 | Socket proxy network to protect Docker |

## Endpoints

| Service     | Endpoint              |
| ----------- | --------------------- |
| Portainer   | http://localhost:9000 |
| Qbittorrent | http://localhost:8080 |

## Requirements

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## References

- https://shantanoo-desai.github.io/posts/technology/portainer-docker-secrets/

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created with :heart: by [Kyle Laverty](https://github.com/kylelaverty)
