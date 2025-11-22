---
## Front matter
title: "Отчёт по лабораторной работе №6"
subtitle: "Настройка пропускной способности глобальной сети с помощью Token Bucket Filter"
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

Основной целью работы является знакомство с принципами работы дисциплины очереди Token Bucket Filter, которая формирует входящий/исходящий
трафик для ограничения пропускной способности, а также получение навыков
моделирования и исследования поведения трафика посредством проведения
интерактивного и воспроизводимого экспериментов в Mininet.

# Задание

1. Задайте топологию (рис. 6.3), состоящую из двух хостов и двух коммутаторов
с назначенной по умолчанию mininet сетью 10.0.0.0/8.
2. Проведите интерактивные эксперименты по ограничению пропускной способности сети с помощью TBF в эмулируемой глобальной сети.
3. Самостоятельно реализуйте воспроизводимые эксперимент по применению
TBF для ограничения пропускной способности. Постройте соответствующие
графики.

# Выполнение лабораторной работы

Задал топологию сети, состоящую из двух хостов и двух коммутаторов (рис. [-@fig:001])

![Топология](image/1.png){ #fig:001 width=70% }

ifconfig (рис. [-@fig:002])

![ifconfig](image/2.png){ #fig:002 width=70% }

Пингование (рис. [-@fig:003])

![Пингование](image/3.png){ #fig:003 width=70% }

iPerf3 сервер (рис. [-@fig:004])

![iPerf3 сервер](image/4.png){ #fig:004 width=70% }

Пропускную способность на 10 Гбит/с на интерфейсе h1-eth0  (рис. [-@fig:005])

![пропускную способность на 10 Гбит/с на интерфейсе h1-eth0](image/5.png){ #fig:005 width=70% }

Проверка пропускной способности  (рис. [-@fig:006])

![Проверка пропускной способности](image/6.png){ #fig:006 width=70% }

Ограничения скорости tbf с параметрами rate = 10gbit, burst = 5,000,000, limit= 15,000,000 (рис. [-@fig:007])

![Ограничения скорости tbf с параметрами rate = 10gbit](image/7.png){ #fig:007 width=70% }

Проверка пропускной способности (рис. [-@fig:008])

![Проверка пропускной способности](image/8.png){ #fig:008 width=70% }

Объединение NETEM и TBF (рис. [-@fig:009])

![Объединение NETEM и TBF](image/9.png){ #fig:009 width=70% }

Проверка пропускной способности (рис. [-@fig:010])

![Проверка пропускной способности](image/10.png){ #fig:010 width=70% }

Ограничение скорости с помощью tbf с параметрами rate=2gbit, burst=1,000,000, limit=2,000,000 (рис. [-@fig:011])

![Ограничение скорости с помощью tbf с параметрами rate=2gbit](image/11.png){ #fig:011 width=70% }

Проверка пропускной способности (рис. [-@fig:012])

![Проверка пропускной способности](image/12.png){ #fig:012 width=70% }

Пропуск. способ-ть 10 Гбит/с, burst=5млн, limit=15млн (рис. [-@fig:015])

![Пропуск. способ-ть 10 Гбит/с, burst=5млн, limit=15млн](image/15.png){ #fig:015 width=70% }

Результат + график (рис. [-@fig:016])

![Результат + график](image/16.png){ #fig:016 width=70% }

TBF на switch1 (рис. [-@fig:017])

![TBF на switch1](image/17.png){ #fig:017 width=70% }

Результат (рис. [-@fig:018])

![Результат](image/18.png){ #fig:018 width=70% }

Второе правило на коммутаторе s1 (рис. [-@fig:019])

![Второе правило на коммутаторе s1](image/19.png){ #fig:019 width=70% }

Результат (рис. [-@fig:020])

![Результат](image/20.png){ #fig:020 width=70% }

Общий график (рис. [-@fig:021])

![Общий график](image/21.png){ #fig:021 width=70% }

# Выводы

Ознакомился с принципами работы дисциплины очереди Token Bucket Filter, которая формирует входящий/исходящий
трафик для ограничения пропускной способности, а также получил навыки
моделирования и исследования поведения трафика посредством проведения
интерактивного и воспроизводимого экспериментов в Mininet.

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