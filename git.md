# Работа с Гитом

## Коммиты

Шаблон оформления коммита:

```
тип[(область действия)]: сообщение
```

### Типы

* `feature` — добавление новой функциональности
* `fix` — исправление бага или доработка
* `wip` — код в процессе разработки
* `chore` — обслуживание кода сборки
* `docs` — всё, что касается документации
* `refactor` — рефакторинг кода приложения
* `test` — всё, что связано с тестированием
* `build` — сборка проекта

### Область действия

Затронутые части (например, `css` или `js`). Указывать необязательно.

### Сообщение

Шаблон оформления сообщения:

```
действие + для какой сущности [+ подробности]
```

## Ветки

* Разработка всегда ведется в ветке `dev`
* Небольшие (однокоммитные) исправления или дополнения можно сделать в ветке `dev`
* Для больших и долгих фич от ветки `dev` ответвляется новая ветка `%FEATURE%`

#### Слияние `%FEATURE%` с веткой `dev`:

```bash
git pull origin dev
git checkout dev
git merge %FEATURE%
```

#### Слияние `dev` с веткой `master`:

```
git checkout master
git merge dev
```

## Теги

### Версионирование

`1.0.0` — *major.minor.patch*

* 1.0.`1` — *patch* — если изменения незначительные (исправление мелких ошибок)
* 1.`1`.0 — *minor* — если появились новые методы или функциональность, не влияющие на уже существующие
* `2`.0.0 — *major* — в случае модификации кода без обратной совместимости с предыдущей версией

## Git-flow

[Шпаргалка](https://danielkummer.github.io/git-flow-cheatsheet/index.ru_RU.html)

### Старт

```bash
# Инициализация
git flow init

# Настройка
Branch name for production releases: master
Branch name for "next release" development: dev
Feature branches: feature/    
Bugfix branches: bugfix/
Release branches: release/
Hotfix branches: hotfix/
Support branches: support/
Version tag prefix: v

# Отправка созданной дев-ветки на удаленный репозиторий
git push origin dev
```

### Фичи

```bash
git flow feature start <name>   # создание
git flow feature finish <name>  # завершение

git flow feature publish <name> # публикация
git flow feature track <name>   # получение
```

### Релизы

```bash
git flow release start <version>   # создание
git flow release finish <version>  # завершение

git flow release publish <version> # публикация
git flow release track <version>   # получение

# Отправка созданного тега на удаленный репозиторий
git push origin --tags
```

### Исправления

```bash
git flow hotfix start <version>  # создание
git flow hotfix finish <version> # завершение

# Отправка созданного тега на удаленный репозиторий
git push origin --tags
```
