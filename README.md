# Ansible Role: redis-cluster

## Requirements

Debian-based distributions, requires ```systemd``` and ```dnspython```.

## Role Variables

redis_cluster_version: 4.0.11

Redis installation.he redis version to use for build from source.

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
redis_cluster_masters:
  - name: redis-01.localhost
    port: 6378
    slaves:
      - name: redis-02.localhost
        port: 6379
  - name: redis-01.localhost
    port: 6379
    slaves:
      - name: redis-02.localhost
        port: 6378

redis_cluster_instances:
  - port: 6378
    protected_mode: 'no'
    cluster_enabled: 'no'
  - port: 6379
    protected_mode: 'no'
    cluster_enabled: 'no'
```

## Example Playbook


```yaml
- hosts: all
  roles:
    - role: redis-cluster.chaordic
```

## License

GPLv3

## Author Information

Cloud Infrastructure Team, Linx Impulse
