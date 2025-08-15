alemuro.mosquitto
=========

[![CI](https://github.com/alemuro/mosquitto-role/actions/workflows/ci.yml/badge.svg)](https://github.com/alemuro/mosquitto-role/actions/workflows/ci.yml)
[![Release](https://github.com/alemuro/mosquitto-role/actions/workflows/release.yml/badge.svg)](https://github.com/alemuro/mosquitto-role/actions/workflows/release.yml)

This role installs and manages the Mosquitto MQTT broker service on Raspbian/Debian devices.

## Features

- Mosquitto MQTT broker installation
- Configurable settings through variables
- User authentication with password files
- Automatic service management
- Support for custom configurations

Role Variables
--------------

| Name                                | Default                 | Description                                                                         |
|-------------------------------------|-------------------------|-------------------------------------------------------------------------------------|
| `alemuro_mosquitto_install_clients` | *yes*                   | `yes` if you wanna install the `mosquitto-clients` package                          |
| `alemuro_mosquitto_settings`        |                         | Object with parameters you wanna configure on mosquitto                             |
| `alemuro_mosquitto_password_file`   | */etc/mosquitto/pwfile* | Location of the passwords file                                                      |
| `alemuro_mosquitto_user_list`       |                         | Users object. One entry per user, with username as identifier and htpasswd as value |

**alemuro_mosquitto_settings**

```yaml
alemuro_mosquitto_settings:
  allow_anonymous: no
  persistence: yes
  log_timestamp: yes
  log_timestamp_format: "%Y-%m-%dT%H:%M:%S"
```

**alemuro_mosquitto_user_list**

```yaml
alemuro_mosquitto_user_list:
  admin: <htpasswd value>
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: pi
  roles:
    - role: alemuro.mosquitto
```

Usage
-----

Install from Ansible Galaxy:

```bash
ansible-galaxy install alemuro.mosquitto
```

## Development

This project uses GitHub Actions for CI/CD. See [CONTRIBUTING.md](CONTRIBUTING.md) for development guidelines.

### Testing

```bash
# Install dependencies
pip install yamllint ansible-lint ansible

# Run tests
yamllint .
ansible-lint
ansible-playbook tests/test.yml --syntax-check
```

License
-------

Apache License
