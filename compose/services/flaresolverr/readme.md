# Flaresolverr

Flaresolverr is a proxy server that bypasses Cloudflare protection by solving Javascript challenges.

In this solution, it is going to be integrated with Prowlarr to bypass Cloudflare protection.

## Setup

There are no additional setup steps needed to get the container to work correctly.

## Connections

This container needs to be connected to the network of Gluetun to access the internet.

```yaml
network_mode: "service:gluetun"
depends_on:
  - gluetun
```

## References

- [Flaresolverr GitHub](https://github.com/FlareSolverr/FlareSolverr)
- [Flaresolverr Container Image](https://hub.docker.com/r/flaresolverr/flaresolverr)
