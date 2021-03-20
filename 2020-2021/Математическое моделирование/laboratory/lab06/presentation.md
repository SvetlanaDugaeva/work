---
## Front matter
lang: ru-RU
title: Отчет по лабораторной работе №6
subtitle: Задача об эпидемиии
author: Дугаева Светлана НФИбд-01-18
institute:
	inst{1}RUDN University, Moscow, Russian Federation
date: 2021, 20 march

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

Исследовать простейшую модель эпидемиии в изолированной системе.

# Выполнение лабораторной работы

## 1)

Код в jupyter notebook для модели эпидемии (рис. -@fig:001):

![Код](images/1.png){ #fig:001 width=50% }

## 2)

Построение графика изменения числа особей в каждой из 3х групп(число заболевших людей - I(t), число здоровых людей с имунитетом - R(t), число восприимчивых к болезни людей, но пока здоровых - S(t)) для случая I(0)<=I* (рис. -@fig:002):

![График для I(0)<=I*](images/2.png){ #fig:002 width=70% }

## 3)

Построение графика изменения числа особей в каждой из 3х групп (рис. -@fig:003):

![График для I(0)>I*](images/3.png){ #fig:003 width=70% }

# Выводы

В ходе данной лабораторной работы мы исследовали модель эпидемии в изолированной системе. А также построили график изменения числа особей в каждой из трёх групп для двух случаев.
