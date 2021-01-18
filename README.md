## Создание нового "продуктового" проекта:

1. Создаем на основе шаблона каталог "продуктового" проекта (dbui-real)

`
mkdir [product-folder] && cd "$_"

git clone https://github.com/iliaschet/dbui-tpl.git .
`

2. Переименовываем удалённый репозиторий с шаблоном "origin" -> "tpl"

`git remote rename origin tpl`

3. Добавляем удаленный репозиторий "продуктового" проекта в качестве origin

`git remote add origin https://github.com/iliaschet/dbui-real.git`

4. Настраиваем локальную ветку main с tpl на origin

`
git branch -M main
git push -u origin main
`

## Быстрый старт:

mkdir dbui-real
cd dbui-real
git clone https://github.com/iliaschet/dbui-tpl.git .
git remote rename origin tpl
git remote add origin https://github.com/iliaschet/dbui-real.git
git branch -M main
git push -u origin main

## Использование ранее созданного "продуктового" проекта в команде:

`
mkdir [product-folder] && cd "$_"

git clone https://github.com/iliaschet/dbui-real.git .
`

`git remote add tpl https://github.com/iliaschet/dbui-tpl.git`


## Действия в "продуктовом" проекте в случае изменения шаблона:

Забираем изменения по шаблону в "продуктовый" проект

`
git fetch tpl

git merge tpl/main
`
Далее происходит решение возможных merge-конфликтов


3. В .gitignore комментируем обратно строку `# app/`

## Дополнительно:

! Проверить какая ветка на какой удаленный репозиторий смотрит:
`git branch -lvv`


npm run init -- --path="https://github.com/iliaschet/dbui-real.git"

npm run existing -- --path="https://github.com/iliaschet/dbui-real.git"
