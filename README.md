# Домашнее задание к занятию 3 «Использование Ansible»  - `Фомичев Анатолий`
Тег: 08-ansible-03-yandex
## Ссылка на домашнее задание - https://github.com/netology-code/mnt-homeworks/tree/MNT-video/08-ansible-03-yandex


![alt text](https://github.com/SLzDevOps/netology-ansible-03/blob/main/Screenshot_781.png).
![alt text](https://github.com/SLzDevOps/netology-ansible-03/blob/main/Screenshot_782.png).
![alt text](https://github.com/SLzDevOps/netology-ansible-03/blob/main/Screenshot_783.png).


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



# Ansible Playbook для ClickHouse, Vector и Lighthouse

## 📌 Описание

Данный playbook предназначен для автоматического развертывания трех сервисов на отдельных хостах в Yandex Cloud (или любом другом окружении с Ubuntu 22.04/24.04):

| Сервис | Назначение |
|:---|:---|
| **ClickHouse** | Колоночная база данных для аналитики и хранения логов |
| **Vector** | Сервис для сбора, обработки и маршрутизации логов |
| **Lighthouse** | Легковесный веб-интерфейс для ClickHouse (на базе Nginx) |

Playbook идемпотентен — повторный запуск не вносит изменений, если система уже настроена.

---

## ⚙️ Параметры

| Параметр | Значение по умолчанию | Описание |
|:---|:---|:---|
| `vector_version` | `0.21.1` | Версия Vector для скачивания |
| `ansible_user` | `ubuntu` | Пользователь для подключения к хостам |
| `ansible_ssh_private_key_file` | `~/.ssh/id_ed25519` | Путь к SSH-ключу |
| `ansible_python_interpreter` | `/usr/bin/python3` | Путь к Python на удаленных хостах |

---


















