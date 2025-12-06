---
## Front matter
title: "Отчёт по лабораторной работе №7"
subtitle: "Введение в работу с данными"
author: "Козлов Всеволод Павлович НФИбд-02-22"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: Arial
romanfont: Arial
sansfont: Arial
monofont: Arial
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Основной целью работы является специализированных пакетов Julia для обработки
данных.

# Задание

1. Используя Jupyter Lab, повторите примеры из раздела 7.2.
2. Выполните задания для самостоятельной работы (раздел 7.4).

# Выполнение лабораторной работы

Считывание данных (рис. [-@fig:001])

![Считывание данных](image/1.png){ #fig:001 width=70% }

Описание датасета (рис. [-@fig:002])

![Описание датасета](image/2.png){ #fig:002 width=70% }

Missing values (рис. [-@fig:003])

![Missing values](image/3.png){ #fig:003 width=70% }

Кластеризация через k-mean (рис. [-@fig:004])

![Кластеризация через k-mean](image/4.png){ #fig:004 width=70% }

KNN (рис. [-@fig:005])

![KNN](image/5.png){ #fig:005 width=70% }

PCA (рис. [-@fig:006])

![PCA](image/6.png){ #fig:006 width=70% }

Линейная регрессия (рис. [-@fig:007])

![Линейная регрессия](image/7.png){ #fig:007 width=70% }

Датапоинты (рис. [-@fig:008])

![Датапоинты](image/8.png){ #fig:008 width=70% }

График регрессии (рис. [-@fig:009])

![График регрессии](image/9.png){ #fig:009 width=70% }

Графики акций (рис. [-@fig:010])

![Графики акций](image/10.png){ #fig:010 width=70% }

# Выводы

Освоил специализированные пакетов Julia для обработки
данных.

# Список литературы
1. Julia 1.5 Documentation. — 2020. — URL: https://docs.julialang.org/en/v1/.
2. Klok H.,Nazarathy Y. Statistics with Julia: Fundamentals for Data Science,Machine Learning
and Artificial Intelligence. — 2020. — URL: https://statisticswithjulia.org/.
3. Ökten G. First Semester in Numerical Analysis with Julia. — Florida State University, 2019. —
DOI: 10.33009/jul.
4. Антонюк В. А. Язык Julia как инструмент исследователя. — М. : Физический факультет
МГУ им. М. В. Ломоносова, 2019.
5. Шиндин А. В. Язык программирования математических вычислений Julia. Базовое
руководство. — Нижний Новгород : Нижегородский госуниверситет, 2016.