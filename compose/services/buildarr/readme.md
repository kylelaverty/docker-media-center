# Buildarr

Buildarr is a service that automatically configures \*Arr services. It is used to configure the \*Arr services with the correct settings and to download the required files.

The configuration is driven from the `buildarr.yml` file. All of the associated configurations are personal preferences and everyone should feel free to change them. Many are based on the TRaSH guide.

One change that is required is that most references will be using `gluetun` is the name since that service is acting as the reverse proxy.

If you have any issues, setting the `BUILDARR_LOG_LEVEL` environment variable to `DEBUG` instead of `INFO` will provide more detailed logs.

## Setup

The first time the container is run it will fail, this is expected and should auto recover. The dependant Arr services need to be updated to support external authentication or have their API key set after their first startup. The `buildarr.yml` file will need to be updated with the correct API keys if that is the route that is taken.

## Connections

The container needs access to the default network to be able to access the internet.

```yaml
networks:
  - default
```

Since this container is intended to update other container's services, it uses them as dependencies to ensure the correct start order.

```yaml
depends_on:
  - gluetun
  - prowlarr
  - flaresolverr
  - radarr
```

## References

- [Buildarr](https://buildarr.github.io/)
- [Buildarr GitHub](https://github.com/buildarr/buildarr)
- [Buildarr Configuration](https://buildarr.github.io/configuration/)
- [Buildarr Container Image](https://hub.docker.com/r/callum027/buildarr)
