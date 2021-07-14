# Ansible Role: Blackbox Exporter

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-blackbox-exporter?style=flat)](https://github.com/OnkelDom/ansible-role-blackbox-exporter/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-blackbox-exporter.svg?style=flat)](https://github.com/OnkelDom/ansible-role-blackbox-exporter/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-blackbox-exporter/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-blackbox-exporter)

## Description

Deploy and manage [blackbox exporter](https://github.com/prometheus/blackbox_exporter) which allows blackbox probing of endpoints over HTTP, HTTPS, DNS, TCP and ICMP.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `blackbox_exporter_version` | 0.19.0 | package version |
| `blackbox_exporter_config_dir` | /etc/blackbox_exporter | config dir |
| `blackbox_exporter_binary_local_dir` | /usr/local/bin | install bin dir |
| `blackbox_exporter_web_listen_address` | 0.0.0.0 | default listen address |
| `blackbox_exporter_web_listen_port` | 9115 | default listen port |
| `blackbox_exporter_system_user` | prometheus | default run user |
| `blackbox_exporter_system_group` | prometheus | default run group |
| `blackbox_exporter_log_level` | warn | default log level |
| `blackbox_exporter_log_format` | json | default log format |
| `blackbox_exporter_limit_nofile` | 8192 | nofile limit in systemd unit defined |
| `blackbox_exporter_cli_flags` | {} | additional configuration flags passed to blackbox exporter binary at startup |
| `blackbox_exporter_configuration_modules` | {} | configure modules |

## Example

### Playbook

```yaml
- hosts: all
  become: true
  roles:
    - onkeldom.blackbox_exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
