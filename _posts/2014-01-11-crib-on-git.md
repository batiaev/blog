---
layout: post
title:  "Шпаргалка по git"
date:   2014-01-11 16:46:11
categories: vcs, git
---
Официальный сайт: [http://git-scm.com/](http://git-scm.com/)


 - Инициализация git:
`git config --global user.name "user name"`
`git config --global user.email "user email"`

 - Создать новый репозиторий:
`git init project-name`

 - Клонировать репозиторий с удаленной машины:
`git clone git@bitbucket.org:afiskon/hs-textgen.git`

 - Добавить файл в репозиторий:
`git add text.txt`

 - Удалить файл:
`git rm text.txt`

 - Текущее состояние репозитория (изменения, неразрешенные конфликты и тп):
`git status`

 - Сделать коммит:
`git commit -a -m "Commit description"`

 - Сделать коммит, введя его описание с помощью $EDITOR:
`git commit -a`


- Замерджить все ветки локального репозитория на удаленный репозиторий:
`git push origin`

 - Аналогично предыдущему, но делается пуш только ветки master:
`git push origin master`

 - Запушить текущую ветку, не вводя целиком ее название:
`git push origin HEAD`

 - Замерджить все ветки с удаленного репозитория:
`git pull origin`

 - Аналогично предыдущему, но накатывается только ветка master:
`git pull origin master`

 - Накатить текущую ветку, не вводя ее длинное имя:
`git pull origin HEAD`

 - Скачать все ветки с origin, но не мерджить их в локальный репозиторий:
`git fetch origin`

 - Аналогично предыдущему, но только для одной заданной ветки:
`git fetch origin master`

 - Начать работать с веткой some_branch (уже существующей):
`git checkout -b some_branch origin/some_branch`

 - Создать новый бранч (ответвится от текущего):
`git branch some_branch`

 - Переключиться на другую ветку (из тех, с которыми уже работаем):
`git checkout some_branch`

 - Получаем список веток, с которыми работаем:
`git branch # звездочкой отмечена текущая ветвь`

 - Просмотреть все существующие ветви:
`git branch -a # | grep something`

 - Замерджить some_branch в текущую ветку:
`git merge some_branch`

 - Удалить бранч (после мерджа):
`git branch -d some_branch`

 - Просто удалить бранч (тупиковая ветвь):
`git branch -D some_branch`

 - Последние изменения:
`git log`

 - История конкретного файла:
`git log file.txt`

 - Аналогично предыдущему, но с просмотром сделанных изменений:
`git log -p file.txt`

 - История с именами файлов и псевдографическим изображением бранчей:
`git log --stat --graph`

 - Изменения, сделанные в заданном коммите:
`git show d8578edf8458ce06fbc5bb76a58c5ca4a58c5ca4`

 - Посмотреть, кем в последний раз правилась каждая строка файла:
`git blame file.txt`

 - Удалить бранч из репозитория на сервере:
`git push origin :branch-name`

 - Откатиться к конкретному коммиту (хэш смотрим в «git log»):
`git reset --hard d8578edf8458ce06fbc5bb76a58c5ca4a58c5ca4`

 - Аналогично предыдущему, но файлы на диске остаются без изменений:
`git reset --soft d8578edf8458ce06fbc5bb76a58c5ca4a58c5ca4`

 - Попытаться обратить заданный commit (но чаще используется branch/reset + merge):
`git revert d8578edf8458ce06fbc5bb76a58c5ca4a58c5ca4`

 - Просмотр изменений (суммарных, а не всех по очереди, как в «git log»):
`git diff # подробности см в "git diff --help"`

 - Используем vimdiff в качестве программы для разрешения конфликтов (mergetool) по умолчанию:
`git config --global merge.tool vimdiff`

 - Отключаем диалог «какой mergetool вы хотели бы использовать»:
`git config --global mergetool.prompt false`

 - Разрешение конфликтов (когда оные возникают в результате мерджа):
`git mergetool`

 - Создание тэга:
`git tag some_tag # за тэгом можно указать хэш коммита`

 - Удаление untracked files:
`git clean -f`

 - «Упаковка» репозитория для увеличения скорости работы с ним:
`git gc`