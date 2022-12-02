# wg-port-forward-mod

a [Docker Mod](https://github.com/linuxserver/docker-mods) for [linuxserver/docker-wireguard](https://github.com/linuxserver/docker-wireguard) that automatically forwards ports through the VPN.

## setup

First, add the variable `DOCKER_MODS=ghcr.io/master-hax/wg-port-forward-mod:latest` in the linuxserver container. Then use the following variables to customize the configuration.

| Env Name | Env Value | Function |
| :----: | :---: | --- |
| `WG_FORWARDED_PORT_<n>` | <port_number> | (required) the port for TCP & UDP packets to be forwarded through e.g.  `WG_FORWARDED_PORT_1 = 8080`,`WG_FORWARDED_PORT_2 = 1234`, etc |
| `WG_PORT_FORWARD_DRYRUN` | "true"/"false" | (optional) false by default. don't actually update the conf, just prints the new conf to stdout
| `WG_PORT_FORWARD_BACKUP_OLD_CONF` | "true/"false" | (optional) false by default. if true, renames the existing wg0.conf to wg0.conf.old instead of overwriting it|
