# Инструкция для работы с Git и удалёнными репозиториями

>Нужно бежать со всех ног, чтобы только оставаться на месте, а чтобы куда-то попасть, надо бежать как минимум вдвое быстрее!
            
                  Льюис Кэррол
***
## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
***Репозиторий*** - это не просто папка, это специально настроенное окружение.
Для создания репозитория в текущем местоположении, необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)


## Добавление отдельных файлов или всех файлов в область подготовленных файлов 


Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>* - эта команда добавит отдельный файл в область подготовленных файлов.
Кроме того, можно добавить все файлы и папки в эту область, набрав "." вместо имени файла: **git add .**


## Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

## Создание коммитов
<<<<<<< HEAD
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***
=======
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

Получится ли конфликт?????   Попробуем его создать и разрешить.

>>>>>>> workbranches
## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с пепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием.
Кроме того, добавив флаг -p, вы можете подробно изучить изменения, внесённые в каждый файл: **git log -p**

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

Команда *git branch* - выводит список всех веток, маркет (*) стоит рядом с той веткой, на которой мы сейчас находимся.

### Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*
При этом мы должны находиться на ветке - "чистовике" - на той ветке, в которую будут вливаться ветки, а <name branch> в данной команде это имя ветки, которую необходимо добавить - "черновик".

*git rebase* - второй способ объединения веток. При этом надо находиться на ветке которую надо влить, указать имя ветки которую вливаем. 

### Удаление веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

## Просмотр изменений до коммита ##
Можно просматривать список изменений, внесённых в репозиторий, используя параметр *diff*. По умолчанию отображаются только изменения, не подготовленные для фиксации. Ввести команду **git diff**
Для просмотра подготовленных изменений необходимо добавить флаг *--staged*. Ввести команду **git diff --staged**
Также можно указать имя файла как параметр и просмотреть изменения, внесённые только в этот файл. Команда **git diff <имя файла>**

## Переименование файлов ##
Переименовать файл или папку можно параметром *mv*. Для него указывается источник и назначение. **git mv <старое имя файла/папки> <новое имя файла/папки>**

## Удаление файла с помощью командной строки ##
Команда **rm <имя файла>** используется в Git для удаления файлов из индекса и рабочей копии. После следующего коммита файл исчезнет и больше не будет отслеживаться. Если вы изменили файл и уже проиндексировали его, вы должны использовать принудительное удаление с помощью параметра *-f*.
Более подробно можно почитать [здесь](https://git-scm.com/book/ru/v2/%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-Git-%D0%97%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2-%D1%80%D0%B5%D0%BF%D0%BE%D0%B7%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B9#r_removing_files)

### Удаление директории

1. Надо выйти из удаляемой папки, если вы находитесь в ней, с помощью команды **cd ..**
2. В командной строке ввести: **rm <название папки>**.
3. Система запросит подтверждение, действительно ли мы хотим удалить всю папку, если да, то введем команду: **rm -r <название папки>**


## Создание файлов и папок

**touch index.html** — Создать файл index.html

**mkdir <название папки>** — Создать папку

## Просмотр заданного коммита

Просмотреть полный список изменений, внесённых конкретным коммитом, можно с помощью параметра show, указав идентификатор или хеш коммита. Значение хеша уникально для каждого коммита, созданного в вашем репозитории: **git show 1af17e73721dbe0c40011b82ed4bb1a7dbe3ce29**
Также можно использовать сокращённый хеш: **git show 1af17e**

## Откат последнего коммита

Откатить последний коммит можно с помощью параметра revert. Создастся новый коммит, содержащий обратные преобразования относительно предыдущего, и добавится к истории текущей ветки: **git revert HEAD**

## Основные команды

* _git init_ – инициализация локального репозитория
* _git status_ – получить информацию от git о его текущем состоянии
* _git add_ – добавить файл или файлы к следующему коммиту
* _git commit -m “message”_ – создание коммита.
* _git log_ – вывод на экран истории всех коммитов с их хеш-кодами
* _git branch_ – посмотреть список веток в репозитории
* _git branch <название ветки>_ – создать новую ветку
* _git checkout <название ветки>_ – переход к другой ветке
* _git branch -d <название ветки>_ – удалить ветку
* _git merge <название ветки>_ - слияние веток
