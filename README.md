# nettop-server

Requires: docker and docker-compose.

Set a DNS `A/AAAA Records` for your `DOMAIN_NAME`, then

```bash
$ docker network create nettop
$ cp .env.example .env
$ alias dc=docker-compose
$ dc build
$ dc up -d && dc logs -f
$ open https://www.${DOMAIN_NAME}
```

## backup

```bash
$ mkdir .backup
$ bin/{caddy,gitlab,fail2ban}_backup
```

## restore

```bash
$ bin/{caddy,gitlab}_restore
```
