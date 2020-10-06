# Ansible Role: blackbox exporter

## Description

Deploy and manage [blackbox exporter](https://github.com/prometheus/blackbox_exporter) which allows blackbox probing of endpoints over HTTP, HTTPS, DNS, TCP and ICMP.

## Requirements

- Ansible >= 2.6 (It might work on previous versions, but we cannot guarantee it)

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
