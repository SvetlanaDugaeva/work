
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

Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Выполнение лабораторной работы

1. Вошла в систему от имени пользователя guest.
2. Создала программу simpleid.c (рис. -@fig:001):

![Программа simpleid.c](im/9.PNG){ #fig:001 }

3. Скомплилировала программу и убедилась, что файл программы создан.
4. Выполнила программу simpleid.
5. Выполните системную программу id, выведенные данные совпадают(id выводит больше информации) .
6. Усложнила программу, добавив вывод действительных идентификаторов и назвала её simpleid2.c (рис. -@fig:002):

![Программа simpleid2.c](im/10.PNG){ #fig:002 } 
 
7. Скомпилировала и запустила simpleid2.c 

Действия из пунктов 3-5 и 7 приведены на (рис. -@fig:003):

![Пункты 3-5 и 7](im/1.PNG){ #fig:003 }

8. От имени суперпользователя выполнила команды по смене владельца и изменению прав на файл simpleid2.
9. Временно повысила свои права с помощью su. Команда chown позволяет изменить владельца файла, а команда chmod позволяет поменять права на файл.
10. Выполнила проверку правильности установки новых атрибутов и смены владельца файла simpleid2.
11. Запустите simpleid2 и id. Выведеные результаты не совпадают, т.к. мы уже изменили владельца файла на суперпользователя.
12. Проделала тоже самое относительно SetGID-бита. В этот раз дынные полностью совпали.

Действия из пунктов 8-12 приведены на (рис. -@fig:004):

![Пункты 8-12](im/2.PNG){ #fig:004 }

13.  Создала программу readfile.c (рис. -@fig:005):

![Программа readfile.c](im/11.PNG){ #fig:005 }

14. Откомпилировала её.
15. Сменила владельца у файла readfile.c (или любого другого текстового файла в системе) и изменила права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог.
16. Проверила, что пользователь guest не может прочитать файл readfile.c.
17. Сменила у программы readfile владельца и установила SetUID-бит.

Действия из пунктов 14-17 приведены на (рис. -@fig:006):

![Пункты 14-17](im/3.PNG){ #fig:006 }

18. Теперь программа readfile может прочитать файл readfile.c (рис. -@fig:007):

![Чтение файла readfile.c](im/4.PNG){ #fig:007 }

19. Также программа readfile может прочитать файл /etc/shadow. Это связано с тем, что мы установили SetUID-бит, и соответственно дали ей права владельца файла(суперпользователя) (рис. -@fig:008):

![Чтение файла /etc/shadow](im/5.PNG){ #fig:008 }

# Исследование Sticky-бита

1. Выяснила, установлен ли атрибут Sticky на директории /tmp.
2. От имени пользователя guest создала файл file01.txt в директории /tmp со словом test.
3. Просмотрела атрибуты у только что созданного файла и разрешила чтение и запись для категории пользователей «все остальные».
4. От пользователя guest2 (не являющегося владельцем) смогла прочитать файл /tmp/file01.txt.
5. От пользователя guest2 дозаписала в файл /tmp/file01.txt слово test2.
6. Проверила содержимое файла.
7. От пользователя guest2 записала в файл /tmp/file01.txt слово test3, стерев при этом всю имеющуюся в файле информацию.
8. Проверила содержимое файла.
9. От пользователя guest2 не смогла удалить файл /tmp/file01.txt.
10. Повысила свои права до суперпользователя и выполнила после этого команду, снимающую атрибут t (Sticky-бит) с директории /tmp.
11. Покинула режим суперпользователя командой exit.

Действия из пунктов 1-11 приведены на (рис. -@fig:009):

![Пункты 1-11](im/6.PNG){ #fig:009 }

12. От пользователя guest2 проверила, что атрибута t у директории /tmp нет.
13. Повторила предыдущие шаги. Удалось выполнить все действия, в том числе и удаление файла.

Действия из пунктов 12-13 приведены на (рис. -@fig:010):

![Пункты 12-13](im/7.PNG){ #fig:010 }

14. Повысила свои права до суперпользователя и вернула атрибут t на директорию /tmp. (рис. -@fig:011):

![Установка атрибута t](im/8.PNG){ #fig:011 }

# Выводы

Изучила механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. Получила практические навыки работы в консоли с дополнительными атрибутами. Рассмотрела работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.  
