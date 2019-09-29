# Ansible Role: postgresql_exporter

[![Build Status](https://travis-ci.org/cimon-io/ansible-postgresql-exporter.svg?branch=master)](https://travis-ci.org/cimon-io/ansible-postgresql-exporter)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)

## Description

Deploy prometheus [postgresql exporter](https://github.com/wrouesnel/postgres_exporter/) using ansible.

## Requirements

- Ansible >= 2.6 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `postgresql_exporter_version` | 1.0.0-RC6.1 | PostgreSQL exporter package version. Also accepts latest as parameter. |
| `postgresql_exporter_system_group` | "postgresql-exp" | System group used to run postgresql_exporter |
| `postgresql_exporter_system_user` | "postgresql-exp" | System user used to run postgresql_exporter |
| `postgresql_exporter_env` | `{ PG_EXPORTER_WEB_LISTEN_ADDRESS: ":9187", DATA_SOURCE_NAME: "postgresql://postgres@localhost:5432/postgres?sslmode=disable" }` | PostgreSQL_exporter environment variables for configuration

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - cimon-io.postgresql-exporter
```

## License

This project is licensed under MIT License.
