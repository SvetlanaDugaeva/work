
---
# Front matter
lang: "ru"
title: "Лабораторная работа №5"
subtitle: "Модель хищник-жертва"
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

Исследовать простейшую модель типа "хищник-жертва" — модель Лотки-Вольтерры.

# Задание

Вариант 29

Для модели «хищник-жертва» (рис. -@fig:001):

![Система ДУ для модели](Images/4.PNG){ #fig:001 width=70%} 

Постройте график зависимости численности хищников от численности жертв, а также графики изменения численности хищников и численности жертв при следующих начальных условиях:

$x_0 = 7, y_{0} = 15$

Найдите стационарное состояние системы.

# Выполнение лабораторной работы

## Теоретическая справка

Простейшая модель взаимодействия двух видов типа «хищник — жертва» - модель Лотки-Вольтерры. Данная двувидовая модель основывается на следующих предположениях:

1. Численность популяции жертв x и хищников y зависят только от времени (модель не учитывает пространственное распределение популяции на занимаемой территории)

2. В отсутствии взаимодействия численность видов изменяется по модели Мальтуса, при этом число жертв увеличивается, а число хищников падает

3. Естественная смертность жертвы и естественная рождаемость хищника считаются несущественными

4. Эффект насыщения численности обеих популяций не учитывается

5. Скорость роста численности жертв уменьшается пропорционально численности хищников (рис. -@fig:002):

![Система ДУ](Images/1.PNG){ #fig:002 width=70%} 

В этой модели x – число жертв, y - число хищников. Коэффициент a описывает скорость естественного прироста числа жертв в отсутствие хищников, с - естественное вымирание хищников, лишенных пищи в виде жертв. 

Вероятность взаимодействия жертвы и хищника считается пропорциональной как количеству жертв, так и числу самих хищников (xy). 

Каждый акт взаимодействия уменьшает популяцию жертв, но способствует увеличению популяции хищников (члены -bxy и dxy в правой части уравнения). 

Математический анализ этой (жесткой) модели показывает, что имеется стационарное состояние A (рис. -@fig:003):

![Эволюция популяции жертв и хищников в модели Лотки-Вольтерры](Images/2.PNG){ #fig:003 width=70%} 

всякое же другое начальное состояние (B) приводит к периодическому колебанию численности как жертв, так и хищников, так что по прошествии некоторого времени система возвращается в состояние B.

Стационарное состояние системы (положение равновесия, не зависящее от времени решение) будет в точке: x0 =a/c , y0 =b/d.

Если начальные значения задать в стационарном состоянии

$x(0) = x_0, y(0) = y_{0}$

то в любой момент времени численность популяций изменяться не будет. При малом отклонении от положения равновесия численности как хищника, так и жертвы с течением времени не возвращаются к равновесным значениям, а совершают периодические колебания вокруг стационарной точки. 

Амплитуда колебаний и их период определяется начальными значениями численностей x(0), y(0). Колебания совершаются в противофазе.

При малом изменении модели (рис. -@fig:004):

![](Images/3.PNG){ #fig:004 width=70%} 

## Решение задачи:

В данной задаче:

x – число хищников, y - число жертв.

a=0.31 - коэффициент естественной смертности хищников

b=0.32 - коэффициент естественного прироста жертв

c=0.054 - коэффициент увеличения числа хищников

d=0.055 - коэффициент смертности жертв 

Стационарное состояние системы будет в точке: x0 =a/c , y0 =b/d. 

1. Построение графика изменения численности хищников (рис. -@fig:005):

![Численность хищников](Images/5.PNG){ #fig:001 width=70%}

2. Построение графика изменения численности жертв (рис. -@fig:006):

![Численность жертв](Images/6.PNG){ #fig:006 width=70%}

3. Построение графика зависимости численности хищников от численности жертв с заданными начальными условиями (рис. -@fig:007):

![Фазовый портрет](Images/7.PNG){ #fig:007 width=70%}

4. Расчет стационарного состояния системы (рис. -@fig:008):

![Стационарное состояние](Images/9.PNG){ #fig:008 width=70%}

$x_0 = 5.74074074074074, y_{0} = 5.818181818181818$

## Построение модели "Хищник-жертва"

Код в jupyter notebook (рис. -@fig:009)

![код](Images/8.PNG){ #fig:009 width=70%}

# Выводы

В ходе данной лабораторной работы мы исследовали модель «хищник – жертва». А также построили график зависимости численности хищников от численности жертв, график изменения численности жертв и график изменения численности хищников, нашли стационарное состояние системы.
