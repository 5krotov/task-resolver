# SUBMODULES

## Клонирование репозитория

После `git clone` выполните `git submodule init`. Далее см. "Подтягивание новых
изменений".

## Добавление подмодуля

Предположим, вы начинаете работу над новой частью приложения. В пространстве
[5krotov](https://github.com/5krotov) создайте репозиторий
`task-resolver-<name>`.

Затем склонируйте текущий репозиторий и выполните:

```bash
git submodule add https://github.com/5krotov/task-resolver-<name> <name>
git commit -m "Add submodule <name>"
git submodule update --remote --merge
```

> Поскольку подмодули, относящиеся к `task-resolver`, соответствуют паттерну
> `task-resolver-<name>`, будет удобно, если здесь директории, соответствующие
> этим репозиториям, будут названы просто `<name>`. Поэтому в bash-команде выше
> используется _git submodule add \<baseurl\>/task-resolver-\<name\>
> **\<name\>**_.

## Подтягивание новых изменений

**GitHub Actions.** Репозиторий обновляется ежедневно, либо каждый раз, когда
кто-то пушит _в него_ (не в сабмодуль).

Если вы хотите получить актуальные изменения из сабмодуля, выполните:

```bash
git submodule update --remote --merge
```

Изменения будут получены вами локально, они не отразятся в удалённом
репозитории, пока вы не выполните:

```bash
git add .
git commit -m "Update submodules"
git push
```

**Чтобы не ломать голову, просто используйте
[update-task-resolver.sh](https://github.com/5krotov/task-resolver-infra/blob/main/tools/update-task-resolver.sh).**

## Ренейминг подмодуля

Если вы хотите изменить название репозитория, сделайте это в UI GitHub, затем в
корне этого проекта выполните:

```bash
git mv <old-name> <new-name>
```

Откройте `.gitmodules` и обновите url, если он был изменён.

Добавьте изменения и запушьте в репозиторий.

## Checkout тега

`git checkout tag` не обновит подмодули до требуемой версии, а лишь укажет на нужные коммиты (см. `git diff` после `checkout`), поэтому корректное перемещение выглядит так:

```bash
git checkout tag
git submodule update --init --recursive --checkout
```
