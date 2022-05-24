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
