---
## Front matter
title: "Отчёт по лабораторной работе №3"
subtitle: "Измерение и тестирование пропускной способности сети. Воспроизводимый эксперимент."
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

Основной целью работы является знакомство с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получение навыков проведения воспроизводимого эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

# Задание

1. Воспроизвести посредством API Mininet эксперименты по измерению пропускной способности с помощью iPerf3.
2. Построить графики по проведённому эксперименту

# Выполнение лабораторной работы

Cоздал подкаталог с примером скрипта (рис. [-@fig:001])

![Подкаталог с примером скрипта](image/1.png){ #fig:001 width=70% }

Изучил содержание скрипта (рис. [-@fig:002])

![Содержание скрипта](image/2.png){ #fig:002 width=70% }

Зпаустил скрипт (рис. [-@fig:003])

![Запуск скрипта](image/3.png){ #fig:003 width=70% }

Посмотрел элементы топологии и завершил работу mininet (рис. [-@fig:004])

![Элементы топологии](image/4.png){ #fig:004 width=70% }

Изменение, позволяющее вывести на экран информацию о хосте h1 (рис. [-@fig:005])

![Вывд на экран информации о хосте h1](image/5.png){ #fig:005 width=70% }

Запуск нового скрипта (рис. [-@fig:006])

![Запуск нового скрипта](image/6.png){ #fig:006 width=70% }

Изменил, чтобы выводилась информация об обоих хостах (рис. [-@fig:007])

![Информация об обоих хостах](image/7.png){ #fig:007 width=70% }

Запуск нового скрипта (рис. [-@fig:008])

![Запуск нового скрипта](image/8.png){ #fig:008 width=70% }

Сделал копию скрипта lab_iperf3_topo.py (рис. [-@fig:009])

![Копию скрипта lab_iperf3_topo.py](image/9.png){ #fig:009 width=70% }

Импорт классов, изменил описание сети, размер CPU и тд (рис. [-@fig:010])

![Импорт классов, описание сети, размер CPU и тд](image/10.png){ #fig:010 width=70% }

Запуск нового скрипта (рис. [-@fig:011])

![Запуск нового скрипта](image/11.png){ #fig:011 width=70% }

В lab_iperf3_topo2.py:
- параметры линков: Отображаются характеристики (10.00Mbit 5ms delay 10.00000% loss)
- конфигурация хостов: Подробная информация о CFS (Completely Fair Scheduler)
Вывод: lab_iperf3_topo2.py показывает более детальную информацию о параметрах сети и планировщике, в то время как lab_iperf3_topo.py вывод упрощен

Сделал копию скрипта lab_iperf3_topo2.py и поместил его в подкаталог iperf (рис. [-@fig:012])

![Копия скрипта lab_iperf3_topo2.py](image/12.png){ #fig:012 width=70% }

Далее будут внесены след. имзенения:
Хосты: Без ограничений CPU
Каналы: 100 Мбит/с, задержка 75 мс, без потерь, без ограничителей
iPerf3 тест:
h2 запускает сервер iPerf3
h1 через 10 сек запускает клиент iPerf3 с сохранением в JSON

Внес изменения в код (рис. [-@fig:013])

![Изменения в коде](image/13.png){ #fig:013 width=70% }

Запуск скрипта (рис. [-@fig:014])

![Запуск скрипта](image/14.png){ #fig:014 width=70% }

Характеристики каналов:
- пропускная способность: 100 Мбит/с
- задержка: 75 мс
- потери: 0% (без потерь)
Конфигурация хостов:
- h1 и h2 - оба настроены с параметрами CFS (без ограничений CPU)
Автоматический тест iperf3:
- h2 запущен как сервер: iperf3 -s -D -1
- h1 запущен как клиент к 10.0.0.2 с сохранением в JSON

Построил графики из получившегося JSON-файла (рис. [-@fig:015])

![Графики из получившегося JSON-файла](image/15.png){ #fig:015 width=70% }

Создал Makefile (рис. [-@fig:016])

![Makefile](image/16.png){ #fig:016 width=70% }

Проверка Makefile, все работает успешно (рис. [-@fig:017])

![Проверка Makefile](image/17.png){ #fig:017 width=70% }

# Выводы

Ознакомился с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получил навыки проведения воспроизводимого эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

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