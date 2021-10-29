
---
# Front matter
lang: "ru"
title: "Лабораторная работа №4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
author: "Дугаева Светлана Анатольевна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: Fira Code
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: xelatex
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Выполнение лабораторной работы

1. От имени пользователя guest определила расширенные атрибуты файла home/guest/dir1/file1 с помощью команды lsattr file(перед этим зашла в каталог dirl). У меня в атрибутах указывается e(extend), удалить нельзя, но на выолнение работы не влияет.
2. Установила командой chmod 600 file на файл права, разрешающие чтение и запись для владельца файла.
3. Попробовала установить на файл расширенный атрибут а от имени пользователя guest командой chattr +a file. В ответ получила отказ от выполнения операции.
4. От имени суперпользователя установила расширенный атрибут a.
5. От пользователя guest проверила правильность установления атрибута командой lsattr file.
6. Выполнила дозапись в файл слова "test" командой echo "test" >> file. А затем выполнила чтение файла командой cat file. Слово test было успешно записано в файл.
7. Попробовала заменить имеющуюся в файле информацию на abcd (команда echo "abcd" > file), получила отказ в выполнении операции. Удалить (rm file) и переименовать файл (mv file file1) также не удалось. 
8. Попробовала установить на файл права, запрещающие чтение и запись для владельца файла (команда chmod 000 file), получила отказ от выполнения операции.

Выполнение пунктов 1-8 представлены на (рис. -@fig:001):

![Проверка возможности выполнения операций для расширенного атрибута a](im/1.PNG){ #fig:001 }

9. Сняла расширенный атрибут a с файла от имени суперпользователя (команда chattr -a file). Нужно было повторить операции, которые раньше не удавалось выполнить, я повторила все операции: (рис. -@fig:002)

![проверка возможности выполнения операций без расширенных атрибутов](im/2.PNG){ #fig:002 }

10. Повторила все действия по шагам, предварительно установив расширенный атрибут i: (рис. -@fig:003)

![проверка для расш. атрибута i](im/3.PNG){ #fig:003 }

Дозапись информации в файл оказалась невозможна. С расш. атрибутом a

Составила таблицу "Установленные права и разрешенные действия": (таб. 1)

|Операция                 |С расш. атрибутом a|Без расш. атрибутов|С расш. атрибутом i|
|-------------------------|-------------------|-------------------|-------------------|
|Дозапись в файл          |+                  |+                  |-                  |
|Чтение файла             |+                  |+                  |+                  |
|Удаление файла           |-                  |+                  |-                  |
|Замена содержимого файла |-                  |+                  |-                  |
|Переименование файла     |-                  |+                  |-                  |
|Смена атрибутов файла    |-                  |+                  |-                  |

: Установленные права и разрешенные действия

Исзодя из таблицы, можно сделать вывод, что с расширенным атрибутом a мы можем только дозаписать информацию в файл и прочитать его содержимое. С расширенным атрибутом i мы можем только прочитать содержимое файла. А без расширенных атрибутов мы можем выполнить любое действие, которое представленно в таблице. Информация получена для прав на файл 600.

# Выводы

В результате выполнения работы я повысила свои навыки использования интерфейса командной строки(CLI), познакомилась на примерах с тем, как используются расширенные атрибуты при разграничении доступа. Имела возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с ее реализацией на практике в ОС Linux. Составила наглядную таблицу, поясняющую какие операции возможны при тех или инных установленных правах. Опробовала действие на практике расширенных атрибутов "a" и "i".  
