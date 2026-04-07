# Ansible Playbook для ClickHouse, Vector и Lighthouse

## Что делает playbook
Устанавливает и настраивает три сервиса на отдельных хостах:
- **ClickHouse** — колоночная БД
- **Vector** — сбор и обработка логов
- **Lighthouse** — веб-интерфейс для ClickHouse (nginx + статика)

## Параметры
| Переменная | Значение по умолчанию | Описание |
|:---|:---|:---|
| `vector_version` | `0.21.1` | Версия Vector |
| `ansible_user` | `ubuntu` | Пользователь для SSH |
| `ansible_ssh_private_key_file` | `~/.ssh/id_ed25519` | Путь к SSH-ключу |

## Теги
- `clickhouse` — только установка ClickHouse
- `vector` — только установка Vector  
- `lighthouse` — только установка Lighthouse

## Запуск
```bash
ansible-playbook -i inventory/prod.yml site.yml --diff
