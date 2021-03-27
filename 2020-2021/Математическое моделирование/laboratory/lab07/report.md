
---
# Front matter
lang: "ru"
title: "Лабораторная работа №7"
subtitle: "Модель эффективности рекламы"
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

Изучение модели распостранения рекламы и ее эффективности.

# Задание

Вариант 29

Постройте график распространения рекламы, математическая модель которой описывается
следующим уравнением:
1) dn/dt=(0.93+0.00003n(t))(N-n(t))
2) dn/dt=(0.00003+0.62n(t))(N-n(t))
3) dn/dt=(0.88cos(t)+0.77cos(2t)n(t))(N-n(t))

При этом объем аудитории N =1120, в начальный момент о товаре знает 19 человек. Для
случая 2 определите в какой момент времени скорость распространения рекламы будет
иметь максимальное значение.

# Выполнение лабораторной работы

## Теоретическая справка

Организуется рекламная кампания нового товара или услуги. Необходимо,
чтобы прибыль будущих продаж с избытком покрывала издержки на рекламу.
Вначале расходы могут превышать прибыль, поскольку лишь малая часть
потенциальных покупателей будет информирована о новинке. Затем, при
увеличении числа продаж, возрастает и прибыль, и, наконец, наступит момент,
когда рынок насытиться, и рекламировать товар станет бесполезным.
Предположим, что торговыми учреждениями реализуется некоторая
продукция, о которой в момент времени t из числа потенциальных покупателей
N знает лишь n покупателей. Для ускорения сбыта продукции запускается реклама
по радио, телевидению и других средств массовой информации. После запуска
рекламной кампании информация о продукции начнет распространяться среди
потенциальных покупателей путем общения друг с другом. Таким образом, после
запуска рекламных объявлений скорость изменения числа знающих о продукции
людей пропорциональна как числу знающих о товаре покупателей, так и числу
покупателей о нем не знающих
Модель рекламной кампании описывается следующими величинами.
Считаем, что dn/dt - скорость изменения со временем числа потребителей,
узнавших о товаре и готовых его купить,
t - время, прошедшее с начала рекламной
кампании, n(t) - число уже информированных клиентов. Эта величина
пропорциональна числу покупателей, еще не знающих о нем, это описывается
следующим образом:
a1(t)(N-n(t)), где
N - общее число потенциальных
платежеспособных покупателей,
a1(t)>0 - характеризует интенсивность
рекламной кампании (зависит от затрат на рекламу в данный момент времени).
Помимо этого, узнавшие о товаре потребители также распространяют полученную
информацию среди потенциальных покупателей, не знающих о нем (в этом случае
работает т.н. сарафанное радио). Этот вклад в рекламу описывается величиной
a2(t)n(t)(N-n(t)) , эта величина увеличивается с увеличением потребителей
узнавших о товаре. Математическая модель распространения рекламы описывается
уравнением:
dn/dt=(a1(t)+a2(t)n(t))(N-n(t))
При a1(t)>>a2(t) получается модель типа Мальтуса,решение которой принимает вид (рис. -@fig:001):

![График решения уравнения модели Мальтуса](Images/1.PNG){#fig:001 width=70%}

В обратном случае, при a1(t)<<a2(t) получаем уравнение логистической кривой (рис. -@fig:002):

![График логистической кривой](Images/2.PNG){#fig:002 width=70%}

## Решение задачи:

Начальные условия в данной задаче:

N = 1120 – все проживающие на острове;
x0 = 19
t0 = 0

1. В первом случае a1(t)>>a2(t) - модель типа Модели Мальтуса:
Для данного уравнения:
dn/dt=(0.93+0.00003n(t))(N-n(t)) 
решение имеет вид (рис. -@fig:003):

![График для 1 случая](Images/3.PNG){ #fig:003 width=70%}

2. Во втором случае случае a1(t)<<a2(t) - уравнение логической прямой:
Для данного уравнения:
dn/dt=(0.00003+0.62n(t))(N-n(t)) 
решение имеет вид (рис. -@fig:004):

![График для 2 случая](Images/4.PNG){ #fig:004 width=70%}

Максимальная скорость распостранения рекламы будет в момент времени t=0.0059

3. Для данного уравнения:
dn/dt=(0.88cos(t)+0.77cos(2t)n(t))(N-n(t))
решение имеет вид (рис. -@fig:005):

![График для 3 случая](Images/5.PNG){ #fig:005 width=70%}

## Построение модели задачи об эпидемии

Код в jupyter notebook для первого случая (рис. -@fig:006):

![код для первого случая](Images/6.PNG){ #fig:006 width=70%}

Код в jupyter notebook для второго случая (рис. -@fig:007):

![код для второго случая](Images/7.PNG){ #fig:007 width=70%}

Код в jupyter notebook для третьего случая (рис. -@fig:008):

![код для третьего случая](Images/8.PNG){ #fig:008 width=70%}

# Выводы

В ходе данной лабораторной работы была изучена модель рекламной кампании, а также
рассмотрены несколько случаев и построены графики для каждого из них.
