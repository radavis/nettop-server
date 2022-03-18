# nettop-server

Requires: docker and docker-compose.

Set a DNS `A/AAAA Records` for your `DOMAIN_NAME`, then

```bash
$ docker network create nettop
$ alias dc=docker-compose
$ cp .env.example .env
$ dc build
$ dc up -d; dc logs -f
$ open https://www.${DOMAIN_NAME}
```

## backup

```bash
$ mkdir .backup
$ bin/caddy_backup
```

## restore

```bash
$ bin/caddy_restore
```
