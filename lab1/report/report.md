---
## Front matter
title: "Отчёт по лабораторной работе №1"
subtitle: "Введение в Mininet."
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

Основной целью работы является развёртывание в системе виртуализации
(например, в VirtualBox) mininet, знакомство с основными командами для работы с Mininet через командную строку и через графический интерфейс.

# Задание

1. Развернуть и настроить виртуальную машину Mininet в VirtualBox, настроив сетевые адаптеры (NAT и Host-Only).
2. Освоить базовые команды Mininet через CLI: запуск топологии, просмотр узлов и связей, проверка связности (ping).
3. Построить сеть в графическом редакторе MiniEdit, проверить связность хостов и настроить автоматическое назначение IP-адресов.

# Выполнение лабораторной работы

Импортировал образ Mininet (рис. [-@fig:001])

![Образ Mininet](image/1.png){ #fig:001 width=70% }

Поменял Graphics Controller (рис. [-@fig:002])

![Graphics Controller](image/2.png){ #fig:002 width=70% }

Изменил адаптеры сет (рис. [-@fig:003])

![Адаптеры сет](image/3.png){ #fig:003 width=70% }

Проверил ifconfig (рис. [-@fig:004])

![ifconfig](image/4.png){ #fig:004 width=70% }

Подключился к машине по ssh (рис. [-@fig:005])

![Подключение к машине по ssh](image/5.png){ #fig:005 width=70% }

Сделал подключение без пароля (рис. [-@fig:006])

![Подключение без пароля](image/6.png){ #fig:006 width=70% }

Указание на использование двух адаптеров при запуске (рис. [-@fig:007])

![Указание на использование двух адаптеров при запуске](image/7.png){ #fig:007 width=70% }

Скачал новую версию Mininet (рис. [-@fig:008])

![Новая версия Mininet](image/8.png){ #fig:008 width=70% }

Обновил исполняемые файлы (рис. [-@fig:009])

![Обновление испрлняемых файлов](image/9.png){ #fig:009 width=70% }

Настройка параметров XTerm (рис. [-@fig:010])

![Настройка параметров XTerm](image/10.png){ #fig:010 width=70% }

Сделал choco install putty и choco install vcxsrv

Запуск минимальной топологии (рис. [-@fig:011])

![Запуск минимальной топологии](image/11.png){ #fig:011 width=70% }

Отображение списка команд интерфейса (рис. [-@fig:012])

![Отображение списка команд интерфейса](image/12.png){ #fig:012 width=70% }

Отображение доступных узлов (рис. [-@fig:013])

![Отображение доступных узлов](image/13.png){ #fig:013 width=70% }

Ввел команду ifconfig на хосте h1 (рис. [-@fig:014])

![ifconfig на хосте h1 ](image/14.png){ #fig:014 width=70% }

Проверил связность (рис. [-@fig:015])

![Проверка связности](image/15.png){ #fig:015 width=70% }

Добавил два хоста и один коммутатор, соединил (рис. [-@fig:016])

![Два хоста и один коммутатор](image/16.png){ #fig:016 width=70% }

ifconfig на h1 (рис. [-@fig:018])

![ifconfig на h1](image/18.png){ #fig:018 width=70% }

ifconfig на h2 (рис. [-@fig:019])

![ifconfig на h2](image/19.png){ #fig:019 width=70% }

Созранил работу, поменял права доступа в каталоге проекта (рис. [-@fig:020])

![Сохранение работы, изменение прав доступа](image/20.png){ #fig:020 width=70% }

# Выводы

Развёрнул в системе виртуализации mininet, ознакомился с основными командами для работы с Mininet через командную строку и через графический интерфейс.

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