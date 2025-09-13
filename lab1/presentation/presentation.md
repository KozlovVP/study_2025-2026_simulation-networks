---
## Front matter
lang: ru-RU
title: Лабораторная Работа №1
subtitle: Введение в Mininet.
author:
  - Козлов В.П.
institute:
  - Российский университет дружбы народов им. Патриса Лумумбы, Москва, Россия

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\makeatother'

## Fonts
mainfont: Arial
romanfont: Arial
sansfont: Arial
monofont: Arial
---


## Докладчик

  * Козлов Всеволод Павлович
  * НФИбд-02-22
  * Российский университет дружбы народов
  * [1132226428@pfur.ru]
  
# Выполнение лабораторной работы

## Цель работы

Основной целью работы является развёртывание в системе виртуализации
(например, в VirtualBox) mininet, знакомство с основными командами для работы с Mininet через командную строку и через графический интерфейс.

## Задание

1. Развернуть и настроить виртуальную машину Mininet в VirtualBox, настроив сетевые адаптеры (NAT и Host-Only).
2. Освоить базовые команды Mininet через CLI: запуск топологии, просмотр узлов и связей, проверка связности (ping).
3. Построить сеть в графическом редакторе MiniEdit, проверить связность хостов и настроить автоматическое назначение IP-адресов.

## Импортировал образ Mininet

![Образ Mininet](image/1.png){ #fig:001 width=70% }

## Поменял Graphics Controller

![Graphics Controller](image/2.png){ #fig:002 width=70% }

## Изменил адаптеры сет

![Адаптеры сет](image/3.png){ #fig:003 width=70% }

## Проверил ifconfig

![ifconfig](image/4.png){ #fig:004 width=70% }

## Подключился к машине по ssh

![Подключение к машине по ssh](image/5.png){ #fig:005 width=70% }

## Сделал подключение без пароля

![Подключение без пароля](image/6.png){ #fig:006 width=70% }

## Указание на использование двух адаптеров при запуске

![Указание на использование двух адаптеров при запуске](image/7.png){ #fig:007 width=70% }

## Скачал новую версию Mininet

![Новая версия Mininet](image/8.png){ #fig:008 width=70% }

## Обновил исполняемые файлы

![Обновление испрлняемых файлов](image/9.png){ #fig:009 width=70% }

## Настройка параметров XTerm

![Настройка параметров XTerm](image/10.png){ #fig:010 width=70% }

# Сделал choco install putty и choco install vcxsrv

## Запуск минимальной топологии

![Запуск минимальной топологии](image/11.png){ #fig:011 width=70% }

## Отображение списка команд интерфейса

![Отображение списка команд интерфейса](image/12.png){ #fig:012 width=70% }

## Отображение доступных узлов

![Отображение доступных узлов](image/13.png){ #fig:013 width=70% }

## Ввел команду ifconfig на хосте h1

![ifconfig на хосте h1](image/14.png){ #fig:014 width=70% }

## Проверил связность

![Проверка связности](image/15.png){ #fig:015 width=70% }

## Добавил два хоста и один коммутатор, соединил

![Два хоста и один коммутатор](image/16.png){ #fig:016 width=70% }

## ifconfig на h1

![ifconfig на h1](image/18.png){ #fig:018 width=70% }

## ifconfig на h2

![ifconfig на h2](image/19.png){ #fig:019 width=70% }

## Созранил работу, поменял права доступа в каталоге проекта 

![Сохранение работы, изменение прав доступа](image/20.png){ #fig:020 width=70% }

## Выводы

Развёрнул в системе виртуализации mininet, ознакомился с основными командами для работы с Mininet через командную строку и через графический интерфейс.