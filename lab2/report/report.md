---
## Front matter
title: "Отчёт по лабораторной работе №2"
subtitle: "Измерение и тестирование пропускной способности сети. Интерактивный эксперимент"
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
получение навыков проведения интерактивного эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

# Задание

1. Установить на виртуальную машину mininet iPerf3 и дополнительное программное обеспечения для визуализации и обработки данных.
2. Провести ряд интерактивных экспериментов по измерению пропускной
способности с помощью iPerf3 с построением графиков.

# Выполнение лабораторной работы

Подключился к машине по ssh (рис. [-@fig:001])

![Подключился к машине по ssh](image/1.png){ #fig:001 width=70% }

Посмотрите IP-адреса машины (рис. [-@fig:002])

![IP-адреса машины](image/2.png){ #fig:002 width=70% }

Устанлвил iperf3 (рис. [-@fig:003])

![Установка iperf3](image/3.png){ #fig:003 width=70% }

Установил необходимое дополнительное программное обеспечение (рис. [-@fig:004])

![Необходимое дополнительное программное обеспечение](image/4.png){ #fig:004 width=70% }

Установил iperf3_plotter (рис. [-@fig:005])

![Установка iperf3_plotter](image/5.png){ #fig:005 width=70% }

Простейшую топология, состоящая из двух хостов и коммутатора
с назначенной по умолчанию mininet сетью 10.0.0.0/8 (рис. [-@fig:006])

![Топология из двух хостов и коммутатора](image/6.png){ #fig:006 width=70% }

Проведем простейший интерактивный эксперимент по измерению пропускной способности с помощью iPerf3 (рис. [-@fig:007])

![Простейший интерактивный эксперимент](image/7.png){ #fig:007 width=70% }

Проанализируем полученный в результате выполнения теста сводный отчёт, отобразившийся как на клиенте, так и на сервере iPerf3. Он содержет следующие данные:

- ID: идентификационный номер соединения -- 7.
- интервал (Interval): временной интервал для периодических отчетов о пропускной способности (по умолчанию временной интервал равен 1 секунде);
- передача (Transfer): сколько данных было передано за каждый интервал времени -- было пепредано от 1.98 до 2.39 GB в секунду;
- пропускная способность (Bitrate): измеренная пропускная способность в каждом временном интервале -- от 17 до 20.5 Gbit/sec;
- Retr: количество повторно переданных TCP-сегментов за каждый временной интервал (это поле увеличивается, когда TCP-сегменты теряются в сети из-за перегрузки или повреждения) -- чем больше пропускная способность, тем больше число повторно переданных  TCP-сегментов. Максимум она достигает 3 при битрейте 20.5 Gbit/sec;
- Cwnd: указывает размер окна перегрузки в каждом временном интервале (TCP использует эту переменную для ограничения объёма данных, которые TCP-клиент может отправить до получения подтверждения отправленных данных) -- это фиксированный параметр равный 8.09 MB.

Проведем аналогичный эксперимент в интерфейсе mininet (рис. [-@fig:008])

![Аналогичный эксперимент в интерфейсе mininet](image/8.png){ #fig:008 width=70% }

Сравним результаты. Увидим, что во втором случае было передано на 4,8 GB больше; пропускная способность увеличилась на 4,1; потери пакетов все также нет.

Эксперимент с указанием времени для передачи (по умол 5) (рис. [-@fig:009])

![Указание времени для передачи](image/9.png){ #fig:009 width=70% }

Выполнение теста пропускной способности с 2-секундным интервалом времени отсчёта (рис. [-@fig:010])

![2-секундный интервал времени отсчёта](image/10.png){ #fig:010 width=70% }

Можно увидеть, что действительно интервал увеличился в два раза, в результате чего в два раза увеличился также вес переданный за один интервал времени, но пропускная способность и суммарные величины очевидно практически не изменились.

Задал на клиенте iPerf3 отправку определённого объёма данных (рис. [-@fig:011])

![Отправка определённого объёма данных](image/11.png){ #fig:011 width=70% }

Изменим в тесте протокол передачи данных с TCP на UDP (рис. [-@fig:012])

![Протокол передачи данных](image/12.png){ #fig:012 width=70% }

Изменим номер порта для отправки/получения пакетов или датаграмм  (рис. [-@fig:013])

![Номер порта ](image/13.png){ #fig:013 width=70% }

Параметр обработки данных только от одного клиента (рис. [-@fig:014])

![Параметр обработки данных только от одного клиента](image/14.png){ #fig:014 width=70% }

Результат в формате json (рис. [-@fig:015])

![Результат в формате json](image/15.png){ #fig:015 width=70% }

Сохраним результат в виде json (рис. [-@fig:016])

![Сохранение результата в виде json](image/16.png){ #fig:016 width=70% }

Сгенерировал выходные данные для файла JSON iPerf3 (рис. [-@fig:017])

![Генерация выходных данных](image/17.png){ #fig:017 width=70% }

Просмотр сгенерированных файлов (рис. [-@fig:018])

![Просмотр сгенерированных файлов](image/18.png){ #fig:018 width=70% }

# Выводы

В результате выполнения данной лабораторной работы я познакомился с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получил навыки проведения интерактивного эксперимента по измерению
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