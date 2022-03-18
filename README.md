# nettop-server

Requires: docker and docker-compose.

Set a DNS `A/AAAA Records` for your `DOMAIN_NAME`, then

```bash
$ docker network create nettop
$ docker volume create --name=caddy-data
$ alias dc=docker-compose
$ cp .env.example .env
$ dc build
$ dc up -d && dc logs -f
$ open https://www.${DOMAIN_NAME}
```

## backup

```bash
$ mkdir .backup
$ bin/*_backup
```

## restore

```bash
$ bin/*_restore
```
