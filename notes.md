## notes

### gitlab backup

Where do backups end up?

```bash
$ dc exec gitlab bash
$ nano /etc/gitlab/gitlab.rb
```

```ruby
# gitlab_rails['manage_backup_path'] = true
# gitlab_rails['backup_path'] = "/var/opt/gitlab/backups"
# gitlab_rails['backup_gitaly_backup_path'] = "/opt/gitlab/embedded/bin/gitaly-backup"
```

```
$ dc exec gitlab bash
$ gitlab-backup create SKIP=builds,registry
```

### portainer password

bcrypt password

```bash
$ docker run --rm httpd:2.4-alpine htpasswd -nbB admin "your-password" | cut -d ":" -f 2
```

Set as `PORTAINER_ADMIN_PASSWORD` in `.env`.

### loki

- https://grafana.com/blog/2021/08/09/new-in-loki-2.3-logql-pattern-parser-makes-it-easier-to-extract-data-from-unstructured-logs/

- https://docs.nginx.com/nginx/admin-guide/monitoring/logging/

- https://grafana.com/docs/loki/latest/logql/log_queries/

- https://grafana.com/docs/loki/latest/logql/metric_queries/

### view default gitlab.rb settings

https://gitlab.com/gitlab-org/omnibus-gitlab/blob/master/files/gitlab-config-template/gitlab.rb.template


### rails console

dc exec -it gitlab gitlab-rails c
