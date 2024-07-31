# Gluetun

Gluetun is a VPN client that supports OpenVPN. You can change the VPN provider by updating the `VPN_PROVIDER` environment variable in the `.env` file. All of the required parameters are laid out in the `example.env` file.

The configuration here also makes use of VPN port forwarding. The configuration also controls the port forwarding file, in this case, `/config/forwarded_port` which is used by other services to get the forwarded port.

## Setup

You will need to create a `.env` file by copying the `example.env` file and then update all of the parameters in the file with the correct values based on your VPN provider.

Every container that wants to use this as a port forwarder will need to have its ports configured in the `ports` section of the `docker-compose.yml` file. By convention the port internally is a separate variable from the port externally and are both defined in the project's `.env` file so they can be referenced in other services.

## Connections

The container needs access to the default network to be able to access the internet.

```yaml
networks:
  - default
```

## References

- [Gluetun GitHub](https://github.com/qdm12/gluetun)
- [Gluetun Wiki GitHub](https://github.com/qdm12/gluetun-wiki)
- [Gluetun Container Image](https://hub.docker.com/r/qmcgaw/gluetun)
