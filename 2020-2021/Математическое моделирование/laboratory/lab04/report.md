
---
# Front matter
lang: "ru"
title: "Лабораторная работа №4"
subtitle: "Модель гармонических колебаний"
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

Изучить модель гармонический колебаний, построить фазовый портрет гармонического осциллятора и решение уравнения гармонического осциллятора для нескольких случаев.

# Задание
Вариант 29

Постройте фазовый портрет гармонического осциллятора и решение уравнения гармонического осциллятора для следующих случаев
1. Колебания гармонического осциллятора без затуханий и без действий внешней силы $x''+5.1x=0$
2. Колебания гармонического осциллятора c затуханием и без действий внешней силы $x''+0.9x'+2x=0$
3. Колебания гармонического осциллятора c затуханием и под действием внешней силы $x''+0.9x'+1.9x=3.3\cos(5t)$
На интервале
$t=(0;38)$ (шаг 0.05) с начальными условиями $x_0 = 0.9, y_{0} = -1.9$

# Выполнение лабораторной работы

## Решение задачи:

Уравнение свободных колебаний гармонического осциллятора имеет следующий вид: 

$x''+2jx'+w_0^2x=$ (1)

где $x$ – переменная, описывающая состояние системы (смещение грузика, заряд конденсатора и т.д.), $j$ – параметр, характеризующий потери энергии (трение в механической системе, сопротивление в контуре), $w_0$ – собственная частота колебаний, $t$ – время.
Уравнение (1) есть линейное однородное дифференциальное уравнение второго порядка, и оно является примером линейной динамической системы.

1. При отсутствии потерь в системе ($j = 0$) вместо уравнения (1) получаем уравнение консервативного осциллятора энергия колебания которого сохраняется во времени:
$x''+w_0^2x=$
В моем варианте, уравнение выглядит следующим образом:
$x'' + 5.1x = 0$, где $w_0^2 = 5.1$.

Решение уравнения колебания гармонического осциллятора без затуханий и без действий внешней силы (рис. -@fig:001):

![Решение1](images/1.png){ #fig:001 width=70% }

Фазовый портрет (рис. -@fig:002):

![Фазовый портрет1](images/2.png){ #fig:002 width=70% }

2. Во втором случае учитываются потери в системе, поэтому j = 0.9, в таком случае уравнение (1) принимает вид:
$x''+0.9x'+2x=0$, где $w_0^2 = 2$.

Решение уравнения колебания гармонического осциллятора c затуханием и без действий внешней силы (рис. -@fig:003):

![Решение2](images/3.png){ #fig:003 width=70% }

Фазовый портрет (рис. -@fig:004):

![Фазовый портрет2](images/4.png){ #fig:004 width=70% }

3. Поскольку в третьем случае учитываются действия внешних сил, находящихся вне системы, то уравнение (1) приравнивается к функции $f(t)=3.3cos(5t)$. Получим: 
$x''+0.9x'+1.9x=3.3\cos(5t)$, где $j = 0.9$, $w_0^2 = 1.9$.

Решение уравнения колебания гармонического осциллятора c затуханием и под действием внешней силы (рис. -@fig:005):

![Решение3](images/5.png){ #fig:005 width=70% }

Фазовый портрет (рис. -@fig:006):

![Фазовый портрет3](images/6.png){ #fig:006 width=70% }

## Построение модели гармонических колебаний

Код в jupyter notebook для первого случая  (рис. -@fig:007)

![код1](images/7.png){ #fig:007 width=70% }

Код в jupyter notebook для второго случая  (рис. -@fig:008)

![код2](images/8.png){ #fig:008 width=70% }

Код в jupyter notebook для третьего случая  (рис. -@fig:009)

![код3](images/9.png){ #fig:009 width=70% }


# Выводы

В ходе лабораторной работы мы построили решения уравнений, а также фазовые портреты для трех возможных моделей гармонического осциллятора.
