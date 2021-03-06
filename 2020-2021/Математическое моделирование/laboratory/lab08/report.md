﻿
---
# Front matter
lang: "ru"
title: "Лабораторная работа №8"
subtitle: "Модель конкуренции двух фирм"
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

Рассмотреть модели конкуренции двух фирм, производящих взаимозаменяемые товары
одинакового качества и находящиеся в одной рыночной нише.

# Задание

Вариант 29

Случай 1: Рассмотрим две фирмы, производящие взаимозаменяемые товары
одинакового качества и находящиеся в одной рыночной нише. Считаем, что в рамках
нашей модели конкурентная борьба ведётся только рыночными методами. То есть,
конкуренты могут влиять на противника путем изменения параметров своего
производства: себестоимость, время цикла, но не могут прямо вмешиваться в
ситуацию на рынке («назначать» цену или влиять на потребителей каким-либо иным
способом.) Будем считать, что постоянные издержки пренебрежимо малы, и в
модели учитывать не будем. В этом случае динамика изменения объемов продаж
фирмы 1 и фирмы 2 описывается следующей системой уравнений (рис. -@fig:001):

![Уравнения динамики изменения объемов продаж для 2х фирм в 1м случае](Images/5.PNG){#fig:001 width=70%}

Случай 2: Рассмотрим модель, когда, помимо экономического фактора
влияния (изменение себестоимости, производственного цикла, использование
кредита и т.п.), используются еще и социально-психологические факторы –
формирование общественного предпочтения одного товара другому, не зависимо от
их качества и цены. В этом случае взаимодействие двух фирм будет зависеть друг 
от друга, соответственно коэффициент перед M1M2
будет отличаться. Пусть в
рамках рассматриваемой модели динамика изменения объемов продаж фирмы 1 и
фирмы 2 описывается следующей системой уравнений (рис. -@fig:002):

![Уравнения динамики изменения объемов продаж для 2х фирм во 2м случае](Images/6.PNG){#fig:002 width=70%}

Для обоих случаев рассмотрим задачу со следующими начальными условиями и параметрами (рис. -@fig:003):

![Начальные условия и параметры](Images/7.PNG){#fig:003 width=70%}

1. Постройте графики изменения оборотных средств фирмы 1 и фирмы 2 без
учета постоянных издержек и с веденной нормировкой для случая 1.

2. Постройте графики изменения оборотных средств фирмы 1 и фирмы 2 без
учета постоянных издержек и с веденной нормировкой для случая 2.

# Выполнение лабораторной работы

## Теоретическая справка

Для построения модели конкуренции хотя бы двух фирм необходимо
рассмотреть модель одной фирмы. Вначале рассмотрим модель фирмы,
производящей продукт долговременного пользования, когда цена его определяется
балансом спроса и предложения. Примем, что этот продукт занимает
определенную нишу рынка и конкуренты в ней отсутствуют.
Обозначим (рис. -@fig:004):

![Условные обозначения](Images/8.PNG){#fig:004 width=70%}

Q(S/p) – функция спроса, зависящая от отношения дохода S к цене p. Она
равна количеству продукта, потребляемого одним потребителем в единицу
времени.
Функцию спроса товаров долговременного использования часто
представляют в простейшей форме (рис. -@fig:005):

![Функция спроса товаров долговременного использования](Images/9.PNG){#fig:005 width=70%}

где q – максимальная потребность одного человека в продукте в единицу времени.
Эта функция падает с ростом цены и при p = pcr (критическая стоимость продукта)
потребители отказываются от приобретения товара. Величина pcr = Sq/k.
Параметр k – мера эластичности функции спроса по цене. Таким образом, функция
спроса в форме (1) является пороговой (то есть, Q(S/p) = 0 при p >= pcr) и обладает
свойствами насыщения.
Уравнения динамики оборотных средств можно записать в виде (рис. -@fig:006):

![Уравнения динамики оборотных средств](Images/10.PNG){#fig:006 width=70%}

Уравнение для рыночной цены p представим в виде (рис. -@fig:007):

![Уравнение для рыночной цены p](Images/11.PNG){#fig:007 width=70%}

Первый член соответствует количеству поставляемого на рынок товара (то
есть, предложению), а второй член – спросу.
Параметр gamma зависит от скорости оборота товаров на рынке. Как правило,
время торгового оборота существенно меньше времени производственного цикла tau.
При заданном M уравнение (3) описывает быстрое стремление цены к
равновесному значению цены, которое устойчиво.
В этом случае уравнение (3) можно заменить алгебраическим соотношением (рис. -@fig:008):

![Алгебраическое соотношение для уравления 3](Images/12.PNG){#fig:008 width=70%}

Из (4) следует, что равновесное значение цены p равно (рис. -@fig:009):

![Равновесное значение цены p](Images/13.PNG){#fig:009 width=70%}

Уравнение (2) с учетом (5) приобретает вид (рис. -@fig:010):

![Измененное уравнение 2](Images/14.PNG){#fig:010 width=70%}

Уравнение (6) имеет два стационарных решения, соответствующих
условию dM/dt = 0  (рис. -@fig:011):

![Стационарные решения для уравнения 6](Images/15.PNG){#fig:011 width=70%}

Из (7) следует, что при больших постоянных издержках (в случае a^2 < 4b)
стационарных состояний нет. Это означает, что в этих условиях фирма не может
функционировать стабильно, то есть, терпит банкротство. Однако, как правило,
постоянные затраты малы по сравнению с переменными (то есть, b << a^2) и играют
роль, только в случае, когда оборотные средства малы. При b << a стационарные
значения M равны (рис. -@fig:012):

![Стационарные значения M](Images/16.PNG){#fig:012 width=70%}

Первое состояние M+ устойчиво и соответствует стабильному
функционированию предприятия. Второе состояние
M- неустойчиво, так, что при M<M-
оборотные средства падают (dM/dt < 0), то есть, фирма идет к 
банкротству. По смыслу
M- соответствует начальному капиталу, необходимому
для входа в рынок.

В обсуждаемой модели параметр sigma всюду входит в сочетании с tau. Это значит,
что уменьшение доли оборотных средств, вкладываемых в производство,
эквивалентно удлинению производственного цикла. Поэтому мы в дальнейшем
положим: sigma = 1, а параметр tau будем считать временем цикла, с учётом сказанного.

## Решение задачи:

1. Рассмотрим две фирмы, производящие взаимозаменяемые товары одинакового
качества и находящиеся в одной рыночной нише. Считаем, что в рамках нашей модели
конкурентная борьба ведётся только рыночными методами. То есть, конкуренты могут влиять
на противника путем изменения параметров своего производства: себестоимость, время цикла,
но не могут прямо вмешиваться в ситуацию на рынке («назначать» цену или влиять на
потребителей каким-либо иным способом.) Будем считать, что постоянные издержки
пренебрежимо малы, и в модели учитывать не будем.

В этом случае динамика изменения объемов продаж фирмы 1 и фирмы 2 описывается
следующей системой уравнений (рис. -@fig:013):

![Уравнения динамики изменения объемов продаж для 2х фирм в 1м случае](Images/5.PNG){#fig:013 width=70%}

Получаем следующий график (рис. -@fig:014):

![График для первого случая](Images/3.PNG){#fig:014 width=70%}

2. Рассмотрим модель, когда, помимо экономического фактора влияния (изменение
себестоимости, производственного цикла, использование кредита и т.п.), используются еще и
социально-психологические факторы – формирование общественного предпочтения одного
товара другому, не зависимо от их качества и цены. В этом случае взаимодействие двух фирм
будет зависеть друг от друга, соответственно коэффициент перед M1M2 будет отличаться.
Пусть в рамках рассматриваемой модели динамика изменения объемов продаж фирмы
1 и фирмы 2 описывается следующей системой уравнений (рис. -@fig:015):

![Уравнения динамики изменения объемов продаж для 2х фирм во 2м случае](Images/6.PNG){#fig:015 width=70%}

Получаем следующий график (рис. -@fig:016):

![График для второго случая](Images/4.PNG){#fig:016 width=70%}


## Построение модели задачи об эпидемии

Код в jupyter notebook для первого случая (рис. -@fig:017):

![код для первого случая](Images/1.PNG){ #fig:017 width=70%}

Код в jupyter notebook для второго случая (рис. -@fig:018):

![код для второго случая](Images/2.PNG){ #fig:018 width=70%}


# Выводы

В ходе данной лабораторной работы мы рассмотрели два случая модели конкуренции
двух фирм, производящих взаимозаменяемые товары одинакового качества и находящиеся в
одной рыночной нише.
