# Ansible Role: Snipe-IT

An Ansible Role that installs [Snipe-IT](https://snipeitapp.com/) on Debian nodes. The application is being deployed on nginx with php-fpm 7.4

## Requirements

Role is self sustainable - it installs all needed prerequisites on the target node.

## Role Variables

Available variables are listed below along with their default values:

```yaml
#if you want to purge all php, nginx, apache2 installation and configuration change it to true
snipe_clean_env: false


snipe_install_dir: /opt/snipe-it
snipe_install_version: 6.0.2
snipe_domain: localhost
snipe_environment: production
snipe_debug_mode: false
snipe_http_server: nginx

#default db settings
snipe_db_host: localhost
snipe_db_port: 3306
snipe_db_name: snipeit
snipe_db_user: root
snipe_db_pass: snipeit

snipe_smtp_host: localhost
snipe_smtp_port: 25
snipe_smtp_user: snipeit
snipe_smtp_pass: snipeit
snipe_smtp_encryption: tls
snipe_email_from: snipeit@host.foo

```

## Example Playbook

```yaml
    - hosts: snipeit
      roles:
         - role: mylocaldevstack.snipeit
```

if you want to change the version of snipe-it

```yaml
    - hosts: snipeit
      vars:
        snipe_install_version: 6.0.2
      roles:
         - role: mylocaldevstack.snipeit
```

## License

Apache
