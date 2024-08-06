# Docker-Based Media Center

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/kylelaverty/docker-media-center/blob/main/LICENSE)

This repo represents my ongoing, incremental work to create a Docker-based media center. The goal is to create a media center that is easy to deploy, maintain, and scale. The media center will be built using Docker containers and Docker Compose. The media center will include services for managing and automating the downloading of media files, streaming media files, and managing indexers and download clients.

## Disclaimer

This project is for educational purposes only. I am not responsible for any misuse of the information provided in this project. I do not condone illegal activities. Use this project at your own risk.

Torrenting is not an illegal activity. It is the sharing of files between users. However, downloading copyrighted material without permission is illegal. Make sure you have the right to download the files you are downloading.

## Table of Contents

- [Services](#services)
- [Services Summary](#services-summary)
- [Services Details](#services-details)
  - [Jellyfin](#jellyfin)
  - [Radarr](#radarr)
  - [Prowlarr](#prowlarr)
- [Internal Networks](#internal-networks)
- [Endpoints](#endpoints)
- [Requirements](#requirements)
- [References](#references)
- [License](#license)
- [Author](#author)

## Services

### Services Summary

| Service                                                                        | Purpose | Description                                        |
| ------------------------------------------------------------------------------ | ------- | -------------------------------------------------- |
| [Docker Socket Proxy](https://docs.linuxserver.io/images/docker-socket-proxy/) | Proxy   | Protect Docker socket with a proxy                 |
| [Gluetun](https://github.com/qdm12/gluetun)                                    | VPN     | OpenVPN client with DNS and firewall configuration |
| [Jellyfin](https://jellyfin.org/)                                              | Media   | Media server                                       |
| [Radarr](https://radarr.video/)                                                | Media   | Movie management and automation                    |
| [Deluge](https://deluge-torrent.org/)                                          | Torrent | BitTorrent client                                  |
| [Prowlarr](https://prowlarr.com/)                                              | Support | Indexer manager with \*Arr Integrations            |
| [Flaresolverr](https://github.com/FlareSolverr/FlareSolverr)                   | Support | Cloudflare bypass integrated with Prowlarr         |
| [Dozzle](https://dozzle.dev/)                                                  | Support | Real-time log viewer                               |
| [Buildarr](https://buildarr.github.io/)                                        | Support | Automated configuration for \*Arr services         |
| [Watchtower](https://containrrr.dev/watchtower/)                               | Support | Automatic container updates                        |

### Services Details

- Bazarr
- Buildarr [Docs](./compose/services/buildarr/readme.md)
- Deluge [Docs](./compose/services/deluge/readme.md)
- Docker Socket Proxy [Docs](./compose/services/socket-proxy/readme.md)
- Dozzle [Docs](./compose/services/dozzle/readme.md)
- Flaresolverr [Docs](./compose/services/flaresolverr/readme.md)
- Gluetun [Docs](./compose/services/gluetun/readme.md)
- Jellyfin
- Jellyseerr
- Kapowarr
- Lidarr
- Prowlarr
- Radarr
- Radarr-Anime
- Readarr
- Sonarr
- Sonarr-Anime
- Watchtower [Docs](./compose/services/watchtower/readme.md)

#### Jellyfin

Jellyfin is a media server that allows you to organize and stream your media files. It will be used to stream media files to your devices.

#### Radarr

Radarr is a service that manages and automates the downloading of movies. It will be used to automatically download movies based on the criteria you set.

Update <AuthenticationMethod>External</AuthenticationMethod> in the `config.xml` file to remove authentication.

#### Prowlarr

Prowlarr is a service that manages indexers and download clients for \*Arr services.

## Internal Networks

| Network      | Subnet          | Description                            |
| ------------ | --------------- | -------------------------------------- |
| default      | --              | Default network for Docker containers  |
| socket_proxy | 192.168.91.0/24 | Socket proxy network to protect Docker |

## Endpoints

| Service      | Type          | Endpoint              |
| ------------ | ------------- | --------------------- |
| Radarr       | Reverse Proxy | http://localhost:7878 |
| Deluge       | Reverse Proxy | http://localhost:8112 |
| Dozzle       | Direct        | http://localhost:8082 |
| Jellyfin     | Reverse Proxy | http://localhost:8096 |
| Flaresolverr | Reverse Proxy | http://localhost:8191 |
| Prowlarr     | Reverse Proxy | http://localhost:9696 |

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
- https://github.com/GitHubMilo/vpn_downloads
- https://trash-guides.info/

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created with :heart: by [Kyle Laverty](https://github.com/kylelaverty)
