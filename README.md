# Task resolver

---
*Сейчас task resolver находится в стадии активного переезда на grpc + tls, grafana и прочие улучшения, поэтому, пожалуйста,
используйте тег stable для ревью, локального запуска и тестирования.  
Отчёт по stable-тэгу находится [тут](./report/REPORT.md).*
---

Здесь ожидается подробное описание назначения и архитектуры приложения.
То, что реализовано на данный момент, можно подсмотреть в [отчёте](./report/REPORT.md).

## Правила контрибьютинга

- [CONTRIBUTING.md](CONTRIBUTING.md)
- [SUBMODULES.md](SUBMODULES.md)

## Запуск 

После клонирования репозитория:

```bash
git checkout stable
# Обновить подмодули до версии, определённой в теге stable
git submodule update --init --recursive --checkout
```

### Docker

В папке `.docker` выполните:

Build:

```bash
  docker-compose -f ./.docker/docker-compose.yaml build
```

Run:

```bash
  docker-compose -f ./.docker/docker-compose.yaml up -d
```

Также можно создавать несколько инстансов сервисов через --scale:

```bash
  docker-compose -f ./.docker/docker-compose.yaml up -d --scale worker=3
```

