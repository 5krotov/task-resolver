# Task resolver

## Overview
Task Resolver - приложение, эмулирующее выполнение задач. Пользователь создаёт задачу, указывая название и сложность
(easy, medium, hard), после чего приложение делает вид, что выполняет его (засыпает на некоторое время).
Пользователь может проверять состояние задачи и просматривать список со всеми задачами по страницам.

Подробнее про, что реализовано на данный момент, можно подсмотреть в [отчёте](./report/REPORT.md).

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

