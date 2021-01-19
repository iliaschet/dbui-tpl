# Шаблон DBUI _
## Создание нового "продуктового" проекта:

### Создаем на основе шаблона каталог "продуктового" проекта

```sh
mkdir [product-folder] && cd "$_" && git clone https://github.com/iliaschet/dbui-tpl.git .
```

, где `[product-folder]` - наименование создаваемого каталога для "продуктового" проекта.

### Запускаем скрипт инициализации нового проекта

`url=[url] npm run init`

, где `[url]` - адрес репозитория "продуктового" проекта.

Скрипт осуществляет последовательно следующие действия:

```javascript
// Переименовываем удалённый репозиторий с шаблоном "origin" -> "tpl"
git remote rename origin tpl
// Добавляем удаленный репозиторий "продуктового" проекта в качестве origin
`git remote add origin [url]`
// Настраиваем локальную ветку main с tpl на origin
`git branch -M main`
`git push -u origin main`
```

## Использование ранее созданного "продуктового" проекта в команде:

### Клонируем "продуктовый" проект

```sh
mkdir [product-folder] && cd "$_" && git clone [url] .
```

, где `[product-folder]` - наименование создаваемого каталога для "продуктового" проекта, а `[url]` - адрес репозитория "продуктового" проекта.

### Запускаем скрипт инициализации

```sh
npm run added
```

## Действия в "продуктовом" проекте в случае изменения шаблона:

Забираем изменения по шаблону в "продуктовый" проект

```
git pull tpl main
```

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
