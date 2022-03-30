# nettop-server

Requires: docker and docker-compose.

Set a DNS `A/AAAA Records` for your `DOMAIN_NAME`, then

```bash
$ cp .env.example .env
$ alias dc=docker-compose
$ dc build
$ dc up -d && dc logs -f
$ open https://gitlab.${DOMAIN_NAME}
```

## backup

```bash
$ mkdir .backup
$ bin/{gitlab,fail2ban}_backup
```

## restore

```bash
$ bin/gitlab_restore
```

## admin gitlab

```bash
$ bin/gitlab_shell
```

## view logs

Visit https://gitlab.${DOMAIN_NAME}/-/grafana. Login as root.

Configuration -> Data sources, Add Loki (http://loki:3100).

Explore -> Select 'Loki' from drop-down -> Click 'Log browser'.
