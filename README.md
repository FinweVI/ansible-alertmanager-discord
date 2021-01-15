# Ansible Role: alertmanager-discord

Provision and manage [alertmanager-discord](https://github.com/benjojo/alertmanager-discord) - plugin to send AlertManager's Alerts through Discord

## Requirements

- Ansible >= 2.8
- Role gantsign.golang

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `alertmanager_discord_version` | latest | alertmanager-discord package version |
| `alertmanager_discord_instance` | {{ ansible_fqdn \| default(ansible_host) \| default(inventory_hostname) }} | Sachet instance name |
| `alertmanager_discord_address` | 127.0.0.1 | Address on which alertmanager-discord listens |
| `alertmanager_discord_port` | 9094 | port on which alertmanager-discord listens |
| `alertmanager_discord_repository` | github.com/benjojo/alertmanager-discord | github link to the source code |
| `alertmanager_discord_default_listen_address` | 127.0.0.1:9094 | Full listening address based on the address and port variable |
| `alertmanager_discord_instances` | [] | yaml list of instances for alertmanager_discord |
| `golang_gopath` | None | Required as the binary will be built from sources |

See the [defaults/main.yml](defaults/main.yml) file for examples.


## Notes

It's Debian-based Only.
It must be possible to make it CentOS (or any other linux-based OS) compatible.
Issues & PR are welcome for any improvement ;-)

This is heavily inspired by [CloudAlchemy]('https://github.com/cloudalchemy/')
