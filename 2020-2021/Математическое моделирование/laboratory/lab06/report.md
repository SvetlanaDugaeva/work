
---
# Front matter
lang: "ru"
title: "Лабораторная работа №6"
subtitle: "Задача об эпидемии"
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

Исследовать простейшую модель эпидемии в изолированной системе.

# Задание

Вариант 29

На одном острове вспыхнула эпидемия. Известно, что из всех проживающих
на острове (N=11 600) в момент начала эпидемии (t=0) число заболевших людей
(являющихся распространителями инфекции) I(0)=260, А число здоровых людей с
иммунитетом к болезни R(0)=48. Таким образом, число людей восприимчивых к
болезни, но пока здоровых, в начальный момент времени S(0)=N-I(0)- R(0)
Постройте графики изменения числа особей в каждой из трех групп.
Рассмотрите, как будет протекать эпидемия в случае:
1) если I(0)<=I*
2) если I(0)>I*


# Выполнение лабораторной работы

## Теоретическая справка

Рассмотрим простейшую модель эпидемии. Предположим, что некая
популяция, состоящая из N особей, (считаем, что популяция изолирована)
подразделяется на три группы. Первая группа - это восприимчивые к болезни, но
пока здоровые особи, обозначим их через S(t). Вторая группа – это число
инфицированных особей, которые также при этом являются распространителями
инфекции, обозначим их I(t). А третья группа, обозначающаяся через R(t) – это
здоровые особи с иммунитетом к болезни.

До того, как число заболевших не превышает критического значения
I*, считаем, что все больные изолированы и не заражают здоровых. Когда
I(t)>I* ,тогда инфицирование способны заражать восприимчивых к болезни особей.
Таким образом, скорость изменения числа S(t) меняется по следующему
закону (рис. -@fig:001):

![скорость изменения числа S(t)](Images/4.PNG){ #fig:001 width=70%}

Поскольку каждая восприимчивая к болезни особь, которая, в конце концов,
заболевает, сама становится инфекционной, то скорость изменения числа
инфекционных особей представляет разность за единицу времени между
заразившимися и теми, кто уже болеет и лечится, т.е. (рис. -@fig:002):

![скорость изменения числа I(t)](Images/5.PNG){ #fig:002 width=70%}

А скорость изменения выздоравливающих особей (при этом приобретающие
иммунитет к болезни) (рис. -@fig:003):

![скорость изменения числа I(t)](Images/6.PNG){ #fig:003 width=70%}

Постоянные пропорциональности alpha, beta - это коэффициенты заболеваемости
и выздоровления соответственно.
Для того, чтобы решения соответствующих уравнений определялось
однозначно, необходимо задать начальные условия .Считаем, что на начало
эпидемии в момент времени t = 0 нет особей с иммунитетом к болезни R(0)=0, а
число инфицированных и восприимчивых к болезни особей
I(0) и S(0) соответственно. Для анализа картины протекания эпидемии необходимо
рассмотреть два случая: 
1) если I(0)<=I*
2) если I(0)>I*

## Решение задачи:

Начальные условия в данной задаче:

N = 11600 – все проживающие на острове;
I(0) = 260 – число заболевших людей;
R(0) = 48 – число здоровых людей с иммунитетом к болезни;
S(0) = N – I(0) – R(0) – число восприимчивых к болезни людей, но пока здоровых.

Зададим зачения alpha и beta:
alpha=0.04, beta=0.07

Для анализа картины протекания эпидемии рассмотрим два случая:

1. если I(0)<=I*

Построение графика изменения числа особей в каждой из групп для первого случая (рис. -@fig:004):

![График для I(0)<=I*](Images/2.PNG){ #fig:004 width=70%}

2. если I(0)>I*

Построение графика изменения числа особей в каждой из групп для второго случая (рис. -@fig:005):

![График для I(0)>I*](Images/3.PNG){ #fig:005 width=70%}

## Построение модели задачи об эпидемии

Код в jupyter notebook (рис. -@fig:006)

![код](Images/1.PNG){ #fig:006 width=70%}

# Выводы

В ходе лабораторной работы мы изучили распространение эпидемии в изолированной среде. А также построили график изменения числа особей в каждой из групп для двух случаев.
