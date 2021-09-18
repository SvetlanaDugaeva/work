
---
# Front matter
lang: "ru"
title: "Лабораторная работа №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
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

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. 

# Выполнение лабораторной работы

Скачала iso-образ CentOS,  запустила VirtualBox, создала ВМ Base, установив все необходимые параматры в соотсвии с описанием к лабораторной работе: (рис. -@fig:001)

![ВМ Base](images/1.PNG){ #fig:001 }

Добавила новый привод оптических дисков и выбрала образ CentOS-6.7: (рис. -@fig:002)

![Окно «Носители» виртуальной машины Base](images/2.PNG){ #fig:002 }

Запустила ВМ и произвела установку операционной системы, поставила пароль на root, а также создала пользователя SDugaeva. Запустила терминал и с помощью команды su перешла под учетную запись root: (рис. -@fig:002)

![Root](images/3.PNG){ #fig:003 }

С помощью команды yum update обновила системные файлы: (рис. -@fig:004)

![Обновление системных файлов](images/4.PNG){ #fig:004 }

Установила программу midnight commander (mc): (рис. -@fig:005)

![Установка mc](images/5.PNG){ #fig:005 }

На Основе ВМ Base создала машину Host2: (рис. -@fig:006)

![ВМ Host2](images/6.PNG){ #fig:006 }

# Выводы
Приобрела практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. 