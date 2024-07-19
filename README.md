# Docker-Based Media Center

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/kylelaverty/docker-media-center/blob/main/LICENSE)

## Services

### Services Summary

| Service                                                                        | Purpose | Description                                        |
| ------------------------------------------------------------------------------ | ------- | -------------------------------------------------- |
| [Docker Socket Proxy](https://docs.linuxserver.io/images/docker-socket-proxy/) | Proxy   | Protect Docker socket with a proxy                 |
| [Qluetun](https://github.com/qdm12/gluetun)                                    | VPN     | OpenVPN client with DNS and firewall configuration |
| [Jellyfin](https://jellyfin.org/)                                              | Media   | Media server                                       |
| [Radarr](https://radarr.video/)                                                | Media   | Movie management and automation                    |
| [Qbittorrent](https://www.qbittorrent.org/)                                    | Torrent | Torrent client                                     |
| [Portainer](https://www.portainer.io/)                                         | Support | Docker management                                  |
| [Dozzle](https://dozzle.dev/)                                                  | Support | Real-time log viewer                               |
| [Watchtower](https://containrrr.dev/watchtower/)                               | Support | Automatic container updates                        |

### Services Details

#### Docker Socket Proxy

Docker Socket Proxy is a service that protects the Docker socket with a proxy. It is used to prevent unauthorized access to the Docker socket.

#### Gluetun

Gluetun is a VPN client that supports OpenVPN. You can change the VPN provider by updating the `VPN_PROVIDER` environment variable in the `.env` file.

#### Jellyfin

Jellyfin is a media server that allows you to organize and stream your media files. It will be used to stream media files to your devices.

#### Radarr

Radarr is a service that manages and automates the downloading of movies. It will be used to automatically download movies based on the criteria you set.

#### Qbittorrent

Qbittorrent is a torrent client that supports downloading and seeding torrents.

#### Portainer

Portainer is a web-based Docker management tool that allows you to manage your Docker containers, images, networks, and volumes. It will be used to check in on the docker setup and see if everything is healthy.

#### Dozzle

Dozzle is a service that provides a real-time log viewer for Docker containers.

#### Watchtower

Watchtower is a service that automatically updates the running Docker containers. Which container is updated can be controlled by the `com.centurylinklabs.watchtower.enable` label in the service's `docker-compose.yml` file.

## Internal Networks

| Network      | Subnet          | Description                            |
| ------------ | --------------- | -------------------------------------- |
| default      | --              | Default network for Docker containers  |
| socket_proxy | 192.168.91.0/24 | Socket proxy network to protect Docker |

## Endpoints

| Service     | Endpoint              |
| ----------- | --------------------- |
| Portainer   | http://localhost:9000 |
| Radarr      | http://localhost:7878 |
| Qbittorrent | http://localhost:8085 |
| Dozzle      | http://localhost:8082 |
| Jellyfin    | http://localhost:8096 |

## Requirements

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## References

- https://shantanoo-desai.github.io/posts/technology/portainer-docker-secrets/
- https://www.smarthomebeginner.com/docker-media-server-2024/
- https://www.web2generators.com/apache-tools/htpasswd-generator
- https://github.com/EdyTheCow/docker-media-center
- https://gitlab.com/rogs/yams
- https://github.com/bcicen/ctop
- https://github.com/veggiemonk/awesome-docker

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created with :heart: by [Kyle Laverty](https://github.com/kylelaverty)
