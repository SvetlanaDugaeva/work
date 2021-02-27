
---
# Front matter
lang: ru-RU
title: "Лабораторная работа №3"
subtitle: "Модель боевых действий"
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

Научиться решать задачу о ведении боевых действий с помощью математического моделирования

# Задание
Вариант 29
Между страной Х и страной У идет война. Численность состава войск
исчисляется от начала войны, и являются временными функциями
x(t) и y(t). В начальный момент времени страна Х имеет армию численностью 202 000 человек,
а в распоряжении страны У армия численностью в 92 000 человек. Для упрощения
модели считаем, что коэффициенты a, b, c, h постоянны. Также считаем
P(t)и Q(t) непрерывные функции.
Постройте графики изменения численности войск армии Х и армии У для
следующих случаев:
1. Модель боевых действий между регулярными войсками
$$ \frac{dx}{dt} = -0,13x(t) -0,51y(t) +0,5sin(t+13)$$
$$ \frac{dy}{dt} = -0,41x(t) -0,15y(t) +0,5cos(t+2)$$

2. Модель ведение боевых действий с участием регулярных войск и
партизанских отрядов
$$ \frac{dx}{dt} = -0,08x(t) -0,76y(t) +sin(2t)+1$$
$$ \frac{dy}{dt}= -0,64x(t)y(t) -0,07y(t) +cos(3t)+1$$

# Выполнение лабораторной работы

## Постановка задачи
1. Зададим начальные значения численности войск: $x_0 = 92000, y_{0} = 202000$

2.  Модель боевых действий между регулярными войсками.
Зададим коэффициент смертности, не связанный с боевыми действиями у первой
армии a=0,13, у второй c=0,15. Коэффициенты эффективности первой и второй армии b=0,51
и h=0,41 соответственно. Функция, описывающая подход подкрепление первой армии,
P(t)= 0,5sin(t+13) 
, подкрепление второй армии описывается функцией
Q(t)= 0,5cos(t+2). 


3. Таким образом решение первой задачи сводится к решению системы дифференциальных уравнений:
$$ \frac{dx}{dt} = -0,13x(t) -0,51y(t) +0,5sin(t+13)$$
$$ \frac{dy}{dt} = -0,41x(t) -0,15y(t) +0,5cos(t+2)$$


4. Модель боевых действий с участием регулярных войск и партизанских отрядов.
 Зададим коэффициент смертности, не связанный с боевыми действиями у первой
армии a=0,08, у второй c=0,07. Коэффициенты эффективности первой и второй армии b=0,76
и h=0,64 соответственно. Функция, описывающая подход подкрепление первой армии,
P(t)= sin(2t)+1 
, подкрепление второй армии описывается функцией
Q(t)= cos(3t)+1.


5. Таким образом решение первой задачи сводится к решению системы дифференциальных уравнений:
$$ \frac{dx}{dt} = -0,08x(t) -0,76y(t) +sin(2t)+1$$
$$ \frac{dy}{dt}= -0,64x(t)y(t) -0,07y(t) +cos(3t)+1$$


## Построение модели боевых действий 

На скриншотах приведен код на Python 3 (рис. -@fig:001, -@fig:002, -@fig:003)

![код](images/1.png){ #fig:001 width=70% }

![код2](images/2.png){ #fig:002 width=70% }

![код3](images/3.png){ #fig:003 width=70% }


Результат для обоих случаев: (рис. -@fig:004, -@fig:005)

![результат1](images/4.png){ #fig:004 width=70% }

![результат2](images/5.png){ #fig:005 width=70% }

Таким образом, в обоих случаях война заканчивается истереблением армии Y, но в случае участия партизанских отрядов это произойдет быстрее.


# Выводы

  - Записала уравнение, описывающее модель боевых действий, с начальными условиями для двух случаев (регулярных войск и для регулярных войск и партизанских отрядов)
  - Построила график численности армий для двух случаев
  - Научилась решать задачу о ведении боевых действий с помощью математического моделирования