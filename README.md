# Ansible Role: Squid Exporter

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-squid-exporter?style=flat)](https://github.com/OnkelDom/ansible-role-squid-exporter/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-squid-exporter.svg?style=flat)](https://github.com/OnkelDom/ansible-role-squid-exporter/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-squid-exporter/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-squid-exporter)

## Description

Deploy and manage prometheus [Squid exporter](https://github.com/pryorda/squid_exporter) using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `squid_exporter_web_listen_port` | 9301 | Exporter port |
| `squid_exporter_firewalld_state` | false | Enabled/Disabled Firewalld and open the port |
| `squid_exporter_config_dir` | /etc/squid_exporter | Configuration folder |
| `squid_exporter_binary_local_dir` | /usr/local/bin | Exporter binary path |
| `squid_exporter_system_user` | prometheus | Exporter running user |
| `squid_exporter_system_group` | prometheus | Exporter running group |
| `squid_exporter_targets` | {} | vCenter targets (see defaults/main.yml) |
| `squid_exporter_allow_firewall` | false | allow firewall access |

## Example

### Playbook

```yaml
- hosts: all
  become: yes
  roles:
    - onkeldom.squid_exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.

