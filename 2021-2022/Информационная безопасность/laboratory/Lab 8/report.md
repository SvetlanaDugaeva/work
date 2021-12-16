
---
# Front matter
lang: "ru"
title: "Лабораторная работа №8"
subtitle: " Элементы криптографии. Шифрование (кодирование) различных исходных текстов одним ключом"
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

Освоить на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом.

# Выполнение лабораторной работы

1. Сначала подключим нужные библеотеки. Затем в переменные hi1 и hi2 запишем 2 наших сообщения, которые требуется зашифровать.
Наиболее удобным вариантом будет написать функцию (crypto), которая принимет на вход 2 открытых сообщения(словами). После этого переведем оба сообщения в 16ричную систему исчисления(для этого используется библеотека sys). 
Создадим случайный ключ(выбор случайного значения от 0 до 255, и затем переведем ключ в 16ричную систему счисления. 
Наложим гамму, то есть выполним операцию сложения по модулю 2(XOR) между элементами полученного случайного ключа и элементами подлежащего сокрытию текста (проведем данную операцию 2 раза, поскольку у нас 2 сообщения). 
Для получания шифротекста переведем значение из 16ричной системы в символную. (рис. -@fig:001):

![Функция кодирования](im/1.PNG){ #fig:001 }

2. Вызовем функцию crypto, она возвращает 2 закодированных сообщения в символьном виде, они нам понадобится для следущего задания. 
Также именно на скриншоте можем увидеть все, что выводит функция (рис. -@fig:002):

![Вызов функции crypto](im/2.PNG){ #fig:002 }

3. Напишем функцию decoder для нахождения ключа для декодирования  2го сообщения. На вход принимается 2 зашифрованных сообщения и одно открытое. 
Для начала переведем оба зашифрованных сообщения и одно открытое в 16ричную систему счисления. 
А затем снова выполним операцию гаммирования, т.е. сложим по модулю 2 между 2мя зашифрованными сообщениями, а потом проделаем ту же операцию между полученным резьтатом и открытым сообщением. 
Таким образом получим второе открытое сообщение в 16 системе сичисления. Затем для наглядности переведем данное сообщение в символьный вид (рис. -@fig:003):

![Функция для получения второго открытого сообщения](im/3.PNG){ #fig:003 }

4. Вызовем функию decoder, передадим ей 2 зашифрованных сообщения и одно открытое в символьном виде.
На эран выводятся сообщения в 16ричной системе счисления, а так же полученное открытое сообщение в символьном виде. Декодировка произведена верно, сообщение совпадает с изначальным (рис. -@fig:004):

![Вызов функции decoder](im/4.PNG){ #fig:004 }

# Выводы

Освоила на практике применение режима однократного гаммирования на примере кодирования различных исходных тестов одним ключом. Закодировала два сообщения с помощью создания случайного ключа и нашла второе открытое сообщение исходя из открытого текста одного сообщения и двух зашифрованных.
