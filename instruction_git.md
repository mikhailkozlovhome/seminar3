# Инструкция по работе с Git

![Эмблема GIT](git.jpg)

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

## Создание нового репозитория

Чтобы создать (инициализировать) новый репозиторий нужно ввести команду:

    git init

## Проверка состония репозитория

Чтобы проверить текущее состояние р епозитория необходимо ввести команду:

    git status

## Добавление файла для отслеживания изменений
Чтобы добавить файл к отслеживанию изменений, необходимо выполнить команду

    git add <имя_файла>

Где <имя_файла>, полное имя файла, который необходимо добавить к отслеживанию изменений

## Запись изменений (коммита) в репозиторий
Чтобы зафиксировать изменения в репозитории, добавленные ранее к отслеживанию, необходимо выполнить команду

    git commit

при выполнении команды откроется окно, в котором можно указать комментарий о создаваемом изменении (коммите)

Чтобы выполнить коммит сразу с комментарием, необходимо выполнить команду с опцией -m:

    git commit -m "message"

Где message - текст комментария

Чтобы выполнить коммит для всейх файлов, ранее добавленных к отслеживанию изменений, необходимо выполнить команду с опций -a:

    git commit -a

Чтобы выполнить коммит для всей файлов, ранее добалвенных к отслеживанию изменений, сразу с комментарием, необходимо выполнить команду с опцией -am:

    git commit -am "message"

Где message - текст комментария

## Просмотр истории внесения изменений в репозиторий

Чтобы посмотреть историю изменений (коммитов) в репозитории, необходимо выполнить команду:

    git log

Чтобы посмотреть историю изменений (коммитов) в репозитории в кратком виде, необходимо выполнить команду:

    git log --oneline

Чтобы посмотреть историю **всех** изменений (коммитов), в том числе выполненных позднее текущего изменения, необходимо выполнить команду:

    git log --all

Опции all и oneline можно использовать совместно.

## Переключение между сохраненными изменениями (коммитами)

Чтобы переключиться между коммитами, необходимо выполнить команду:

    git checkout <hash>

где hash - идентификатор коммита    

## Просмотр изменений (различий) между коммитами

Чтобы посмотреть изменения (различия) между коммитами необходимо выполнить команду:

    git diff <hash1> <hash2>

где hash1 и hash2 - идентификаторы коммитов различия между которыми необходимо просмотреть.

Чтобы посмотреть различия между текущим состоянием репозитория и последним коммитом, необходимо выполнить команду:

    git diff

## Исключение файлов из отслеживания

Чтобы намеренно исключить файл или файлы из отслеживания, необходимо в папке с репозиторием создать файл с именем ".gitignore" и указать в нем имя или шаблон имени файла или файлов, которые необходимо исключить из отслеживания. Для отслеживания изменений в файле ".gitignore", необходимо его добавить к списку отслеживаемых файлов командой "git add .gitignore".

## Работа с ветками в git

### Просмотр списка веток

Для того чтобы просмотреть список веток, существующих в репозитории, необходимо выполнить коианду:

    git branch

при этом ветка, которая является в настоящий момент активной будет помечена символом "*", например "*master".

### Создание новых веток в git

Для того чтобы создать новую ветку в git, необходимо выполнить команду:

    git branch <имя ветки>

где <имя ветки> - имя новой ветки, которую мы создаем.

### Переключение между ветками

Для того чтобы переключиться между ветками, необходимо выполнить команду:

    git checkout <имя_ветки>

где <имя_ветки> - имя ветки на которую хотим переключиться.

### Слияние веток в git

Для того чтобы слияние веток, необходимо выполнить команду:

    git merge <имя_ветки>

где <имя_ветки> - имя ветки, которая вливается в текущую активную ветку.

### Merge конфликт

При выполнении слияния веток, в которых выполнены изменения в одних и тех же строках, возникает конфликт слияния или "merge" конфликт. Для его разрешения VSCODE визуализирует конфликт и предлагает несколько вариантов его разрешения, см. скриншот:

![Merge конфликт](mrg_conflict.jpg)

где при выборе в верхней строке визулизации:
+ "Accept Current Change" - примениться изменение текущей ветки;
+ "Accept Incoming Change" - применяться изменения входящей ветки;
+ "Accept Both Changes" - применяться изменения обеих веток;

### Удаление веток

Для того чтобы удалить ветку, необходимо выполнить команду:

    git branch -d <имя_ветки>

где <имя_ветки> - имя удаляемой ветки.

### Просмотр графического представления коммитов

Для того чтобы просмотреть графическое представление коммитов, необходимо выполнить команду:

    git log --graph

![git_graph](git_graph.jpg)
