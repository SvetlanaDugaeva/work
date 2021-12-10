
---
# Front matter
lang: "ru"
title: "Лабораторная работа №7"
subtitle: " Элементы криптографии. Однократное гаммирование"
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

Освоить на практике применение режима однократного гаммирования.

# Выполнение лабораторной работы

1. Сначала подключим нужные библеотеки. Затем в переменную hi запишем наше сообщение, которое требуется зашифровать.
Наиболее удобным вариантом будет написать функцию (crypto), которая принимет на вход открытое сообщение(словами). После этого переведем сообщение в 16ричную систему исчисления(для этого используется библеотека sys). 
Создадим случайный ключ(выбор случайного значения от 0 до 255, и затем переведем ключ в 16ричную систему счисления. В дополнение я перевела ключ в символьный вид.
Наложим гамму, то есть выполним операцию сложения по модулю 2(XOR) между элементами полученного случайного ключа и элементами подлежащего сокрытию текста 
Для получания шифротекста переведем значение из 16ричной системы в символную. (рис. -@fig:001):

![Функция кодирования](im/1.PNG){ #fig:001 }

2. Вызовем функцию crypto, она возвращает закодированное сообщение в символьном виде, оно нам понадобится для следущего задания. 
Также именно на скриншоте можем увидеть все, что выводит функция (рис. -@fig:002):

![Вызов функции crypto](im/2.PNG){ #fig:002 }

3. Напишем функция для нахождения ключа для декодирования сообщения. На вход принимается открытое сообщение и зашифрованное. 
Для начала переведем оба сообщения в 16ричную систему счисления. 
А затем снова выполним операцию гаммирования, т.е. сложим по модулю 2. 
Таким образом получим ключ. Затем для наглядности переведем ключ в символьный вид (рис. -@fig:003):

![Функция для получения ключа](im/3.PNG){ #fig:003 }

4. Вызовем функию decoder, передадим ей открытый ключ и шифротекст в символьном виде.
На эран выводится ключ в 16ричной системе счисления и в символьном виде (рис. -@fig:004):

![Вызов функции decoder](im/4.PNG){ #fig:004 }

# Выводы

Освоила на практике применение режима однократного гаммирования. Закодировала сообщение с помощью создания случайного ключа и нашла ключ исходя из открытого текста и шифротекста.
