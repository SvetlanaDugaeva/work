---
## Front matter
lang: ru-RU
title: Отчет по лабораторной работе №7
subtitle: Модель эффективности рекламы
author: Дугаева Светлана НФИбд-01-18
institute:
	inst{1}RUDN University, Moscow, Russian Federation
date: 2021, 27 march

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---
# Цель работы

Изучение модели распостранения рекламы и ее эффективности.

# Выполнение лабораторной работы

## 1)

Код в jupyter notebook для первого случая уравнение: 
dn/dt=(0.93+0.00003n(t))(N-n(t)) (рис. -@fig:006):

![код для первого случая](Images/6.PNG){ #fig:006 width=70%}

## 2)

Код в jupyter notebook для второго случая уравнение:
dn/dt=(0.00003+0.62n(t))(N-n(t)) (рис. -@fig:007):

![код для второго случая](Images/7.PNG){ #fig:007 width=70%}

## 3)

Код в jupyter notebook для третьего случая уравнение:
dn/dt=(0.88cos(t)+0.77cos(2t)n(t))(N-n(t)) (рис. -@fig:008):

![код для третьего случая](Images/8.PNG){ #fig:008 width=70%}

## 4)

В первом случае a1(t)>>a2(t) - модель типа Модели Мальтуса:
Для данного уравнения:
dn/dt=(0.93+0.00003n(t))(N-n(t)) 
решение имеет вид (рис. -@fig:003):

![График для 1 случая](Images/3.PNG){ #fig:003 width=70%}

## 5)

Во втором случае случае a1(t)<<a2(t) - уравнение логической прямой:
Для данного уравнения:
dn/dt=(0.00003+0.62n(t))(N-n(t)) 
решение имеет вид (рис. -@fig:004):

![График для 2 случая](Images/4.PNG){ #fig:004 width=70%}

## 6)

Для данного уравнения:
dn/dt=(0.88cos(t)+0.77cos(2t)n(t))(N-n(t))
решение имеет вид (рис. -@fig:005):

![График для 3 случая](Images/5.PNG){ #fig:005 width=70%}

# Выводы

В ходе данной лабораторной работы была изучена модель рекламной кампании, а также
рассмотрены несколько случаев и построены графики для каждого из них.
