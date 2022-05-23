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
