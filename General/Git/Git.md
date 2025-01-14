Git — это распределенная система контроля версий, позволяющая отслеживать изменения в коде и работать над проектом нескольким разработчикам одновременно.
## 1. Как отменить опубликованный коммит

### Команда `git revert`:

- Отменяет изменения указанного коммита, создавая новый коммит.
- Команда: `git revert [commit SHA]`
- Отправка изменений в удалённый репозиторий: `git push [repository]/branch-name`

### Удаление коммита в личной ветке:

- Используйте интерактивный ребейз: `git rebase -i`
- Отметьте коммит флагом `drop` для полного удаления из истории.
- Отправка изменений: `git push [repository]/branch-name --force`


## 2. Разница между `git pull` и `git fetch`

### `git pull`:

- Извлекает данные с сервера и автоматически делает слияние с текущей веткой.

### `git fetch`:

- Получает данные с удаленного репозитория, но не выполняет слияние.

## 3. Что такое “staging area” или “index” в GIT?

- Область подготовленных файлов (staging area) — файл в Git-директории с информацией об изменениях, которые попадут в следующий коммит.


## 4. Команда `git stash`

- Сохраняет измененное состояние рабочей директории или файла в хранилище незавершенных изменений.
- Позволяет применить изменения обратно позже.
- Просмотр спрятанных изменений: `git stash list`
- Применение изменений: `git stash apply`


## 5. Как найти список файлов, изменившихся в определенном коммите

- Команда `git log` с флагами:
    - `--stat` — показывает список и количество измененных файлов, количество добавленных и удаленных строк.
    - `--name-status` — показывает список измененных и удаленных файлов.
- Для конкретного коммита: `git show [commit SHA]`

## 6. Команда `git config`

- Просмотр и настройка конфигурации git репозитория.


## 7. Из чего состоит коммит в GIT

- Односвязный список объектов с измененными файлами и ссылкой на предыдущий коммит.
- Содержит информацию об авторе, метки времени и сообщение коммита.


## 8. Как создать GIT-репозиторий

### Версионирование существующего проекта:

- Перейти в папку с проектом и выполнить: `git init`

### Клонирование удаленного репозитория:

- Команда: `git clone [url]`

## 9. Как объединить несколько коммитов в один

- Используйте перебазирование в интерактивном режиме: `git rebase -i HEAD~3`
- В редакторе заменить `pick` на `squash` для нужных коммитов.

## 10. Команда `git bisect`

- Выполняет бинарный поиск по истории коммитов для обнаружения проблемного коммита.
- Команды:
    - `git bisect start`
    - `git bisect bad`
    - `git bisect good [хеш коммита]`

## 11. Настройка проверки кода перед коммитом

- Используйте хук `pre-commit` в конфигурационном файле `.git/hooks`.

## 12. Модели ветвления в GIT

### Git flow:

- Две постоянные ветки: `master` и `develop`
- Временные ветки: `feature-`, `release-`, `hotfix-`

## 13. Как узнать, было ли слияние ветки в `master`

- Команда: `git branch --merged`