---
## Front matter
lang: ru-Ru 
title: "Лабораторная работа №1"
subtitle: "Работа с git"
author: "Гнатюк Анастасия Станиславовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной работы является изучение работы с git, а именно знакомство с командами, с помощью которых мы сможем работать с репозиториями, файлами, папками и ветками.

# Теоретическое введение

<p>Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года; координатор — Дзюн Хамано.

<p>Среди проектов, использующих Git, — ядро Linux, Swift, Android, Drupal, Cairo, GNU Core Utilities, Mesa, Wine, Chromium, Compiz Fusion, FlightGear, jQuery, PHP, NASM, MediaWiki, DokuWiki, Qt, ряд дистрибутивов Linux.

<p>Программа является свободной и выпущена под лицензией GNU GPL версии 2. По умолчанию используется TCP-порт 9418.

# Выполнение лабораторной работы

## 1.1 Подготовка
### 1.1.1 Установка имени и электронной почты

<p> git config --global user.name "Your Name"
<p> git config --global user.email "your_email@whatever.com"

### 1.1.2 Параметры установки окончаний строк

<p> Настройка core.autocrlf с параметрами true и input делает все переводы
строк текстовых файлов в главном репозитории одинаковы.
core.autocrlf true - git автоматически конвертирует CRLF->LF при коммите и обратно LF->CRLF при выгрузке кода из репозитория на файловую систему
(используют в Windows). core.autocrlf input - конвертация CRLF в LF только
при коммитах (используют в Mac/Linux).
<p> Если core.safecrlf установлен в true или warm, git проверяет, если преобразование является обратимым для текущей настройки core.autocrlf.
core.safecrlf true - отвержение необратимого преобразования lf<->crlf.
<p> Полезно, когда специфические бинарники похожие на текстовые файлы.
core.safecrlf warn - печать только предупреждение, но принимает необратимый переход.

<p> Для пользователей Windows:
<p> git config --global core.autocrlf true
<p> git config --global core.safecrlf true


### 1.1.3 Установка отображения unicode

<p> По умолчанию, git будет печатать не-ASCII символов в именах файлов в виде восьмеричных последовательностей \nnn. Что бы избежать нечитаемых строк, установите соответствующий флаг.

<p> git config --global core.quotepath off

![Рис.1:](скрины/28.jpg)

## 1.2 Создание проекта
### 1.2.1 Создайте страницу «Hello, World»

<p> Начните работу в пустом рабочем каталоге с создания пустого каталога с именем hello, затем войдите в него и создайте там файл с именем hello.html.

<p> mkdir hello
<p> cd hello
<p> touch hello.html
<p> echo "Hello, World!" > hello.html

![Рис.2:](скрины/36.jpg)

### 1.2.2 Создание репозитория и добавление файла в репозиторий 

<p> Добавим файл в репозиторий.

<p> git add hello.html
<p> git commit -m "Initial Commit"

![Рис.3:](скрины/88.jpg)

### 1.2.3 Проверка состояние репозитория

<p> Используйте команду git status, чтобы проверить текущее состояние репозитория.

<p> git status 

![Рис.4:](скрины/89.jpg)

## 1.3 Внесение изменений
### 1.3.1  Измените страницу «Hello, World»

<p> Добавим кое-какие HTML-теги к нашему приветствию. Измените содержимое файла hello.html на:

![Рис.6:](скрины/пупсик.jpg)

<p> Проверьте состояние рабочего каталога.

<p> git status

![Рис.5:](скрины/90.jpg)

![Рис.7:](скрины/87.jpg)

![Рис.8:](скрины/79.jpg)

## 1.4 Индексация изменений 
### 1.4.1 Коммит изменений

<p> Теперь выполните команду git, чтобы проиндексировать изменения. Проверьте состояние.

<p> git add hello.html
<p> git status

![Рис.9:](скрины/41.jpg)

<p> Сделайте коммит и проверьте состояние.

<p> git commit

<p> Откроется редактор.

<p> В первой строке введите комментарий: «Added h1 tag». Сохраните файл и выйдите из редактора (для этого в редакторе по-умолчанию (Vim) вам нужно нажать клавишу ESC, ввести :wq и нажать Enter).
<p> Теперь еще раз проверим состояние.

<p> git status

<p> Рабочий каталог чистый, можно продолжить работу

![Рис.10:](скрины/92.jpg)

### 1.4.2 Добавьте стандартные теги страницы
Измените страницу «Hello, World», чтобы она содержала стандартные теги html
и body.

![Рис.11:](скрины/пупсик2.jpg)

![Рис.12:](скрины/ААААА.jpg)

<p> Теперь добавьте это изменение в индекс git.

<p> git add hello.html

<p> Теперь добавьте заголовки HTML (секцию head) к странице «Hello, World».

![Рис.13:](скрины/96.jpg)

<p> Проверьте текущий статус:

<p> git status
<p> Обратите внимание на то, что hello.html указан дважды в состоянии. Первое изменение (добавление стандартных тегов) проиндексировано и готово к
коммиту. Второе изменение (добавление заголовков HTML) является непроиндексированным. Если бы вы делали коммит сейчас, заголовки не были бы сохранены в репозиторий.

![Рис.14:](скрины/93.jpg)

<p> Произведите коммит проиндексированного изменения (значение по умолчанию), а затем еще раз проверьте состояние.

<p> git commit -m "Added standard HTML page tags"
<p> git status

![Рис.15:](скрины/91.jpg)

<p> Состояние команды говорит о том, что hello.html имеет незафиксированные
изменения, но уже не в буферной зоне.
<p> Теперь добавьте второе изменение в индекс, а затем проверьте состояние с
помощью команды git status.

<p> git add .
<p> git status

![Рис.16:](скрины/95.jpg)

### 1.4.3 История

<p> Получим список произведенных изменений:

<p> git log

![Рис.17:](скрины/45.jpg)

### 1.4.4 Получение старых версий

<p> Получите хэши предыдущих версий

<p> git log

<p> Изучите данные лога и найдите хэш для первого коммита. Он должен быть в
последней строке данных. Используйте этот хэш-код (достаточно первых 7 знаков) в команде ниже. Затем проверьте содержимое файла hello.html.

<p> git checkout "hash"
<p> cat hello.html

![Рис.18:](скрины/37.jpg)

<p> Вернитесь к последней версии в ветке master

<p> git checkout master
<p> cat hello.html

![Рис.19:](скрины/13.jpg)

<p> master — имя ветки по умолчанию. Переключая имена веток, вы попадаете на
последнюю версию выбранной ветки.

### 1.4.5 Создание тегов версий

<p> Давайте назовем текущую версию страницы hello первой (v1).
<p> Создайте тег первой версии

<p> git tag v1

<p> Теперь текущая версия страницы называется v1.
<p>Теги для предыдущих версий Давайте создадим тег для версии, которая идет
перед текущей версией и назовем его v1-beta. В первую очередь нам надо переключиться на предыдущую версию. Вместо поиска до хэш, мы будем использовать ^, обозначающее «родитель v1». Вместо обозначения v1^ можно использовать v1~1. Это обозначение можно определить как «первую версию предшествующую v1».

<p> git checkout v1^
<p> cat hello.html

<p> Это версия c тегами html и body, но еще пока без head. Давайте сделаем ее версией v1-beta.

<p> git tag v1-beta

![Рис.20:](скрины/78.jpg)
![Рис.21:](скрины/80.jpg)

## 1.8 Удаление коммиттов из ветки

<p> git revert является мощной командой, которая позволяет отменить любые коммиты в репозиторий. Однако, и оригинальный и «отмененный» коммиты видны в
истории ветки (при использовании команды git log).
<p> Часто мы делаем коммит, и сразу понимаем, что это была ошибка. Было бы
неплохо иметь команду «возврата», которая позволила бы нам сделать вид, что
неправильного коммита никогда и не было. Команда «возврата» даже предотвратила бы появление нежелательного коммита в истории git log.

<p> Давайте сделаем быструю проверку нашей истории коммитов. Выполните:

<p> git log

<p> Мы видим, что два последних коммита в этой ветке — «Oops» и «Revert Oops».
<p> Давайте удалим их с помощью сброса.

<p> Но прежде чем удалить коммиты, давайте отметим последний коммит тегом, чтобы потом можно было его найти.

<p> git tag oops


![Рис.22:](скрины/40.jpg)

![Рис.23:](скрины/84.jpg)

<p> Глядя на историю лога, мы видим, что коммит с тегом «v1» является коммитом, предшествующим ошибочному коммиту. Давайте сбросим ветку до этой точки.
<p> Поскольку ветка имеет тег, мы можем использовать имя тега в команде сброса (если она не имеет тега, мы можем использовать хэш-значение).

<p> git reset --hard v1
<p> git log

<p> Наша ветка master теперь указывает на коммит v1, а коммитов Oops и Revert Oops в ветке уже нет. Параметр --hard указывает, что рабочий каталог должен быть обновлен в соответствии с новым head ветки.

## 1.9 Работа с ветками
Пора сделать наш hello world более выразительным. Так как это может занять
некоторое время, лучше переместить эти изменения в отдельную ветку, чтобы
изолировать их от изменений в ветке master.

### 1.9.1 Создайте ветку

<p> Давайте назовем нашу новую ветку «style».
<p>Выполните:

<p> git checkout -b style
<p> git status
<p> git checkout -b  

<p> Обратите внимание, что команда git status сообщает о том, что вы находитесь в ветке «style».

![Рис.24:](скрины/10.jpg)

### 1.9.2 Просмотрите текущие ветки

<p> Теперь у нас в репозитории есть две отличающиеся ветки. Используйте следующую лог-команду для просмотра веток и их отличий.
<p> Выполните:

<p> git log --graph --all

![Рис.25:](скрины/30.jpg)

### 1.9.3 Слияние веток

<p> Слияние переносит изменения из двух веток в одну. Давайте вернемся к ветке style и сольем master с style.
<p>Выполните:

<p> git checkout style
<p> git merge master
<p> git log --graph --all

![Рис.26:](скрины/15.jpg)
![Рис.27:](скрины/32.jpg)

<p> Путем периодического слияния ветки master с веткой style вы можете переносить из master любые изменения и поддерживать совместимость изменений
style с изменениями в основной ветке.

### 1.9.4 Сброс ветки style

<p> Вернемся на ветке style к точке перед тем, как мы слили ее с веткой master. Мы можем сбросить ветку к любому коммиту. По сути, это изменение указателя ветки на любую точку дерева коммитов.
<p> В этом случае мы хотим вернуться в ветке style в точку перед слиянием с master.
<p> Нам необходимо найти последний коммит перед слиянием.
<p> Выполните:

<p> git checkout style
<p> git log --graph

<p> Мы видим, что коммит «Updated index.html» был последним на ветке style
перед слиянием. Давайте сбросим ветку style к этому коммиту.
Выполните:

<p> git reset --hard "hash"

![Рис.28:](скрины/61.jpg)

### 1.9.5 Перебазирование

<p> Используем команду rebase вместо команды merge. Мы вернулись в точку до первого слияния и хотим перенести изменения из ветки master в нашу ветку style.
<p> На этот раз для переноса изменений из ветки master мы будем использовать
команду git rebase вместо слияния.
<p> Выполните:

<p> git checkout style
<p> git rebase master
<p> git log --graph

![Рис.29:](скрины/57.jpg)


# Вывод
Мы поработали с git, изучили и попробовали некоторые команды.




