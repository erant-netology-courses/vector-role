# Ansible Role: vector

Установка и настройка Vector — легковесного агента для сбора и передачи логов в ClickHouse.

## Requirements

- ClickHouse с базой `logs` (создаётся автоматически)
- ОС: Ubuntu 20.04/22.04 или Debian 11/12
- Ansible 2.9+

## Role Variables

| Переменная | Значение по умолчанию | Описание |
|-----------|----------------------|----------|
| `vector_version` | `0.55.0` | Версия Vector |
| `vector_url` | `https://packages.timber.io/vector/{{ vector_version }}/vector-{{ vector_version }}-x86_64-unknown-linux-gnu.tar.gz` | URL для скачивания |
| `vector_install_dir` | `/opt/vector` | Директория установки |
| `vector_interval` | `1` | Интервал генерации демо-логов |
| `clickhouse_host` | `127.0.0.1` | Адрес ClickHouse для отправки логов |

## Dependencies

Нет.

## Example Playbook

```yaml
- name: Install Vector
  hosts: vector
  vars:
    clickhouse_host: "192.168.1.20"
  roles:
    - vector
```

## Inventory

```yaml
vector:
  hosts:
    vector-01:
      ansible_connection: local
```

## Tags

Теги не заданы.

## License

MIT

## Author

@erant-netology-courses