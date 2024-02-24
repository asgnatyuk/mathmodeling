---
## Front matter
lang: ru-Ru 
title: "Лабораторная работа №3"
subtitle: "Модель боевых действий"
author: "Гнатюк Анастасия Станиславовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
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

Построить модель боевых действий через графики функций.

# Теоретическое введение

![Рис.1: Теория](screens/1.png)

<p>

![Рис.2: Теория](screens/2.png)

<p>

![Рис.3: Теория](screens/3.png)

<p>

![Рис.4: Теория](screens/4.png)

<p>

![Рис.5: Теория](screens/5.png)

<p>

![Рис.6: Теория](screens/6.png)

<p>

![Рис.7: Теория](screens/7.png)

<p>

![Рис.8: Теория](screens/8.png)


# Выполнение лабораторной работы

![Рис.9: Условия задачи](screens/10.png)

<p>

![Рис.10: Условия задачи](screens/11.png)

<p> Распишем наше решение в виде кода на julia в блокноте. Делаем всё то же самое, как и в теоритической части, просто меняя параметры на свои.

<p>

![Рис.11: Код на julia](screens/9.png)

<p> Обзательно прописываем вывод в виде создания двух изображений с графиками функций.

<p> 1-й случай:

![Рис.12: График функций для 1-ого случая](screens/lab03_1.png)

<p>

<p> 2-й случай:

![Рис.13: График функций для 2-ого случая](screens/lab03_2.png)

<p>

<p> Чтобы не было грустно - посмотри на котика.

<p>

![Рис.14: Милый котик](screens/10.jpg)


# Вывод

<p> Мы построили модель боевых действий через графики функций.



