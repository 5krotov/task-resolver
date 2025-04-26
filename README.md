# Task resolver

Здесь ожидается подробное описание назначения и архитектуры приложения.
То, что реализовано на данный момент, можно подсмотреть в [отчёте](./report/REPORT.md).

## Правила контрибьютинга

- [CONTRIBUTING.md](CONTRIBUTING.md)
- [SUBMODULES.md](SUBMODULES.md)

## Запуск 

### Docker

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

