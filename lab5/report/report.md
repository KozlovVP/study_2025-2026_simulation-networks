---
## Front matter
title: "Отчёт по лабораторной работе №5"
subtitle: "Эмуляция и измерение потерь пакетов в глобальных сетях"
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

Основной целью работы является получение навыков проведения интерактивных экспериментов в среде Mininet по исследованию параметров сети,
связанных с потерей, дублированием, изменением порядка и повреждением
пакетов при передаче данных. Эти параметры влияют на производительность
протоколов и сетей.

# Задание

1. Задайте простейшую топологию, состоящую из двух хостов и коммутатора
с назначенной по умолчанию mininet сетью 10.0.0.0/8.
2. Проведите интерактивные эксперименты по по исследованию параметров
сети, связанных с потерей, дублированием, изменением порядка и повреждением пакетов при передаче данных.
3. Реализуйте воспроизводимый эксперимент по добавлению правила отбрасывания пакетов в эмулируемой глобальной сети. На экран выведите сводную
информацию о потерянных пакетах.
4. Самостоятельно реализуйте воспроизводимые эксперименты по исследованию параметров сети, связанных с потерей, изменением порядка и повреждением пакетов при передаче данных. На экран выведите сводную
информацию о потерянных пакетах.

# Выполнение лабораторной работы

Задал простейшую топологию, просмотрел ifconfig (рис. [-@fig:001])

![ifconfig](image/1.png){ #fig:001 width=70% }

Пропинговал (рис. [-@fig:002])

![Пингование](image/2.png){ #fig:002 width=70% }

На h1 добавил 10% потерь пакетов  (рис. [-@fig:003])

![На h1 10% потерь пакетов](image/3.png){ #fig:003 width=70% }

10% packet loss

На h2 тоже добавил 10% потерь пакетов (рис. [-@fig:004])

![На h2 тоже 10% потерь пакетов](image/4.png){ #fig:004 width=70% }

22% packet loss

Добавил на интерфейсе узла h1 коэффициент потери пакетов 50% (рис. [-@fig:007])

![На интерфейсе узла h1 коэффициент потери пакетов 50%](image/7.png){ #fig:007 width=70% }

Добавил на интерфейсе узла h1 0,01% повреждения пакетов (рис. [-@fig:008])

![На интерфейсе узла h1 0,01% повреждения пакетов](image/8.png){ #fig:008 width=70% }

25% пакетов - сразу, остальные - с задержкой (рис. [-@fig:009])

![25% пакетов - сразу, остальные - с задержкой](image/9.png){ #fig:009 width=70% }

h1 задал правило c дублированием 50% пакетов (рис. [-@fig:010])

![Правило c дублированием 50% пакетов](image/10.png){ #fig:010 width=70% }

Написал скрипт (рис. [-@fig:011])

![python скрипт](image/11.png){ #fig:011 width=70% }

Создал Makefile (рис. [-@fig:012])

![Makefile](image/12.png){ #fig:012 width=70% }

Зпуск make (рис. [-@fig:013])

![Зпуск make](image/13.png){ #fig:013 width=70% }

Написал lab_netem_loss.py (рис. [-@fig:014])

![lab_netem_loss.py](image/14.png){ #fig:014 width=70% }

Запуск lab_netem_loss.py (рис. [-@fig:015])

![Запуск lab_netem_loss.py](image/15.png){ #fig:015 width=70% }

Написал lab_netem_reorder.py (рис. [-@fig:016])

![lab_netem_reorder.py](image/16.png){ #fig:016 width=70% }

Запуск lab_netem_reorder.py (рис. [-@fig:017])

![Запуск lab_netem_reorder.py](image/17.png){ #fig:017 width=70% }

Написал lab_netem_corruption.py (рис. [-@fig:018])

![Написал lab_netem_corruption.py](image/18.png){ #fig:018 width=70% }

Запуск lab_netem_corruption.py (рис. [-@fig:019])

![Запуск lab_netem_corruption.py](image/19.png){ #fig:019 width=70% }

# Выводы

Получил навыки проведения интерактивных экспериментов в среде Mininet по исследованию параметров сети,
связанных с потерей, дублированием, изменением порядка и повреждением
пакетов при передаче данных.

# Список литературы

1.  **Официальный сайт и репозиторий Mininet**  
    - Mininet Official Website. – URL: [http://mininet.org/](http://mininet.org/)  
    - Mininet GitHub Repository. – URL: [https://github.com/mininet/mininet](https://github.com/mininet/mininet)  

2.  **Документация по системам виртуализации и графическому интерфейсу**  
    - VirtualBox Official Manual. – URL: [https://www.virtualbox.org/manual/UserManual.html](https://www.virtualbox.org/manual/UserManual.html)  
    - X Window System Protocol Documentation. – URL: [https://www.x.org/releases/current/doc/xproto/x11protocol.html](https://www.x.org/releases/current/doc/xproto/x11protocol.html)  

3.  **Вспомогательные ресурсы**  
    - VcXsrv Windows X Server. – URL: [https://sourceforge.net/projects/vcxsrv/](https://sourceforge.net/projects/vcxsrv/)  
    - Xming X Server. – URL: [http://www.straightrunning.com/XmingNotes/](http://www.straightrunning.com/XmingNotes/)  