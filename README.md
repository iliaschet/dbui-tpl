## Создание нового "продуктового" проекта:

1. Создаем на основе шаблона каталог "продуктового" проекта (dbui-real)

```sh
mkdir [product-folder] && cd "$_"
git clone https://github.com/iliaschet/dbui-tpl.git .
```

, где `[product-folder]` - наименование каталога с "продуктовым" проектом.

2. Запускаем скрипт инициализации нового проекта

`npm run init [https://github.com/iliaschet/dbui-real.git]`

, где `[https://github.com/iliaschet/dbui-real.git]` - адрес репозитория "продуктового" проекта.

Скрипт осуществляет последовательно следующие действия:

---
```
- Переименовываем удалённый репозиторий с шаблоном "origin" -> "tpl"

`git remote rename origin tpl`

- Добавляем удаленный репозиторий "продуктового" проекта в качестве origin

`git remote add origin [url]`

- Настраиваем локальную ветку main с tpl на origin

`git branch -M main`

`git push -u origin main`
```
----

## Использование ранее созданного "продуктового" проекта в команде:

```sh
mkdir [product-folder] && cd "$_"
git clone https://github.com/iliaschet/dbui-real.git .
git remote add tpl https://github.com/iliaschet/dbui-tpl.git
```

## Действия в "продуктовом" проекте в случае изменения шаблона:

Забираем изменения по шаблону в "продуктовый" проект

`git pull tpl main`

или 

```
git fetch tpl
git merge tpl/main
```

Далее происходит решение возможных merge-конфликтов

## Дополнительно:

Для проверки списка имен и адресов удаленных репозиториев:
`git remote -v`

Для проверки списка веток и на какой удаленный репозиторий они смотрят:
`git branch -lvv`
