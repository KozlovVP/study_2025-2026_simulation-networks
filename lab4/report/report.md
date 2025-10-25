---
## Front matter
title: "Отчёт по лабораторной работе №4"
subtitle: "Эмуляция и измерение задержек в глобальных сетях"
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

Основной целью работы является знакомство с NETEM — инструментом для
тестирования производительности приложений в виртуальной сети, а также
получение навыков проведения интерактивного и воспроизводимого экспериментов по измерению задержки и её дрожания (jitter) в моделируемой сети
в среде Mininet.

# Задание

1. Задайте простейшую топологию, состоящую из двух хостов и коммутатора
с назначенной по умолчанию mininet сетью 10.0.0.0/8.
2. Проведите интерактивные эксперименты по добавлению/изменению задержки, джиттера, значения корреляции для джиттера и задержки, распределения
времени задержки в эмулируемой глобальной сети.
3. Реализуйте воспроизводимый эксперимент по заданию значения задержки
в эмулируемой глобальной сети. Постройте график.
4. Самостоятельно реализуйте воспроизводимые эксперименты по изменению
задержки, джиттера, значения корреляции для джиттера и задержки, распределения времени задержки в эмулируемой глобальной сети. Постройте
графики.

# Выполнение лабораторной работы

Топология, состоящая из двух хостов и коммутатора с назначенной по умолчанию mininet сетью 10.0.0.0/8 (рис. [-@fig:001])

![Топология, состоящая из двух хостов и коммутатора](image/1.png){ #fig:001 width=70% }

Просмотрео ifconfig (рис. [-@fig:002])

![ifconfig](image/2.png){ #fig:002 width=70% }

Пропинговал (рис. [-@fig:003])

![Пингование](image/3.png){ #fig:003 width=70% }

min = 0.047ms; 
avg = 0.59ms;
max = 3.063ms;
mdev = 1.106ms.

На хосте h1 добавил задержку в 100 мс к выходному интерфейсу (рис. [-@fig:004])

![Задержка в 100 мс](image/4.png){ #fig:004 width=70% }

На хосте h2 также добавить задержку в 100 миллисекунд (рис. [-@fig:005])

![h2 также добавить задержку](image/5.png){ #fig:005 width=70% }

Изменил задержку со 100 мс до 50 мс для отправителя h1 и h2 (рис. [-@fig:006])

![50 мс для отправителя h1 и h2](image/6.png){ #fig:006 width=70% }

Восстановил конфигурацию по умолчанию (рис. [-@fig:007])

![Конфигурация по умолчанию](image/7.png){ #fig:007 width=70% }

h1 задержка в 100 мс со случайным отклонением 10 мс (рис. [-@fig:008])

![h1 задержка в 100 мс со случайным отклонением 10 мс](image/8.png){ #fig:008 width=70% }

h1 задержку в 100 мс с вариацией +- 10мс и значением корреляции в 25%(рис. [-@fig:009])

![h1 задержку в 100 мс с вариацией +- 10мс и значением корреляции в 25%](image/9.png){ #fig:009 width=70% }

Нормальное распределение задержки на узле h1 (рис. [-@fig:010])

![Нормальное распределение задержки на узле h1](image/10.png){ #fig:010 width=70% }

Создал скрипт для эксперимента lab_netem_i.py (рис. [-@fig:011])

![скрипт для эксперимента lab_netem_i.py](image/11.png){ #fig:011 width=70% }

скрипт для визуализации ping_plot (рис. [-@fig:012])

![скрипт для визуализации ping_plot](image/12.png){ #fig:012 width=70% }

Makefile (рис. [-@fig:013])

![Makefile](image/13.png){ #fig:013 width=70% }

Запуск make (рис. [-@fig:014])

![Запуск make](image/14.png){ #fig:014 width=70% }

График (рис. [-@fig:015])

![График](image/15.png){ #fig:015 width=70% }

скрипт для вычисления на основе данных файла ping.dat (рис. [-@fig:016])

![скрипт для вычисления на основе данных файла ping.dat](image/16.png){ #fig:016 width=70% }

Воспроизводимый эксперимент 2 (рис. [-@fig:017])

![Воспроизводимый эксперимент 2](image/17.png){ #fig:017 width=70% }

Воспроизводимый эксперимент 3 (рис. [-@fig:018])

![Воспроизводимый эксперимент 3](image/18.png){ #fig:018 width=70% }

Воспроизводимый эксперимент 4 (рис. [-@fig:019])

![Воспроизводимый эксперимент 4](image/19.png){ #fig:019 width=70% }

Воспроизводимый эксперимент 5 (рис. [-@fig:020])

![Воспроизводимый эксперимент 5](image/20.png){ #fig:020 width=70% }

Воспроизводимый эксперимент 6 (рис. [-@fig:021])

![Воспроизводимый эксперимент 6](image/21.png){ #fig:021 width=70% }

# Выводы

Озакомился с NETEM — инструментом для
тестирования производительности приложений в виртуальной сети, а также
получил навыков проведения интерактивного и воспроизводимого экспериментов по измерению задержки и её дрожания (jitter) в моделируемой сети
в среде Mininet.

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