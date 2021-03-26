# Ansible Role: blackbox-exporter

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-blackbox-exporter?style=flat)](https://github.com/OnkelDom/ansible-role-blackbox-exporter/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-blackbox-exporter.svg?style=flat)](https://github.com/OnkelDom/ansible-role-blackbox-exporter/tags)

## Description

Deploy and manage [blackbox exporter](https://github.com/prometheus/blackbox_exporter) which allows blackbox probing of endpoints over HTTP, HTTPS, DNS, TCP and ICMP.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `blackbox_exporter_create_consul_agent_service` | "true" | Add consul agent config snipped |
| `blackbox_exporter_version` | 0.15.1 | Blackbox exporter package version |
| `blackbox_exporter_web_listen_address` | 0.0.0.0:9115 | Address on which blackbox exporter will be listening |
| `blackbox_exporter_cli_flags` | {} | Additional configuration flags passed to blackbox exporter binary at startup |
| `blackbox_exporter_configuration_modules` | http_2xx: { prober: http, timeout: 5s, http: '' } | |

## Example

### Playbook

```yaml
- hosts: all
  become: true
  roles:
    - ansile-role-blackbox-exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
