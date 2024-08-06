# Prowlarr

Prowlarr is a service that manages indexers and download clients for \*Arr services.

## Setup

Prowlarr can be configured by Buildarr but when Prowlarr first starts up the `AuthenticationMethod` is set so it prompts to login. This must be updated to `External` in the `config.xml` file to remove authentication. Once that is done, Buildarr will be able to configure Prowlarr.

## Connections

This container needs to be connected to the network of Gluetun to access the internet.

```yaml
network_mode: "service:gluetun"
depends_on:
  - gluetun
```

It also depends on the deluge container to download torrents.

```yaml
depends_on:
  - deluge
```

## References

- [Prowlarr](https://prowlarr.com/)
- [Prowlarr GitHub](https://github.com/Prowlarr/Prowlarr)
- [Prowlarr Wiki](https://wiki.servarr.com/prowlarr)
- [Prowlarr Container Image](https://hub.docker.com/r/linuxserver/prowlarr)
