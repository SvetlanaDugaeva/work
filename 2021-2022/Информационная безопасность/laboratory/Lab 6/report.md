
---
# Front matter
lang: "ru"
title: "Лабораторная работа №6"
subtitle: "Мандатное разграничение прав в Linux"
author: "Дугаева Светлана Анатольевна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: Fira Code
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: xelatex
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Подготовка лабораторного стенда

В конфигурационном файле /etc/httpd/httpd.conf необходимо задать параметр ServerName:
ServerName test.ru
чтобы при запуске веб-сервера не выдавались лишние сообщения об ошибках, не относящихся к лабораторной работе.
Выполнила здание параметра с помощью команды 
echo "ServerName test.ru" >> /etc/httpd/httpd.conf

Также необходимо проследить, чтобы пакетный фильтр был отключён или в своей рабочей конфигурации позволял подключаться к 80-у и 81-у портам протокола tcp. 
Отключила фильтр можно командами
iptables -F
iptables -P INPUT ACCEPT 
iptables -P OUTPUT ACCEPT

# Выполнение лабораторной работы

1.  Вошла в систему с полученными учётными данными и убедилась, что SELinux работает в режиме enforcing политики targeted с помощью команд getenforce и sestatus

Действия из подготовки лабораторного стенда и пункта 1 выполнения лабораторной работы представленны на (рис. -@fig:001):

![П. 1 выполения ЛР и подготовка](im/1.PNG){ #fig:001 }

2.  Обратилась с помощью браузера к веб-серверу, запущенному на моем компьютере, и убедилась, что последний работает:
service httpd status
3. Нашла веб-сервер Apache в списке процессов, определила его контекст безопасности: пользователь system_u, политика ролевого разделения system_r, тип https_t, уровень доступа s0.

Действия пунктов 2-3 предствленны на (рис. -@fig:002):

![Статус веб-сервера и политика безопасности](im/2.PNG){ #fig:002 }

4.  Посмотрела текущее состояние переключателей SELinux для Apache с помощью команды
sestatus -b httpd
Многие из них находятся в положении «off». (рис. -@fig:003):

![Состояние переключателей](im/3.PNG){ #fig:003 }

5. Посмотрела статистику по политике с помощью команды seinfo 
6.  Определила тип файлов и поддиректорий, находящихся в директории /var/www, с помощью команды ls -lZ /var/www:
7. пределю тип файлов, находящихся в директории /var/www/html с помощью команды 
ls -lZ /var/www/html.
8.  Определю круг пользователей, которым разрешено создание файлов в директории /var/www/html.
Создавать файлы можно только суперпользователю, который является владельцем.

Действия пунктов 5-8 представленны на (рис. -@fig:004):

![Пункты 5-8](im/4.PNG){ #fig:004 }

9.  Создам от имени суперпользователя html-файл /var/www/html/test.html следующего содержания:
<html>
<body>test</body>
</html>
10.  Проверю контекст созданного мной файла. 
По умолчанию вновь созданным файлам в директории /var/www/html присваивается контекст unconfined_u:object_r:httpd_sys_conent_t:s0

Действия пунктов 9-10 представленны на (рис. -@fig:005):

![Пункты 9-10](im/5.PNG){ #fig:005 }

11.  Обратилась к файлу через веб-сервер, введя в браузере адрес
http://127.0.0.1/test.html. Файл был успешно отображён (рис. -@fig:006):

![Обращение к файлу через веб-сервер](im/6.PNG){ #fig:006 }

12. Изучила справку man httpd_selinux (рис. -@fig:007):

![Справка о контекстах](im/7.PNG){ #fig:007 }

Контекст созданного мной файла: 
unconfined_u : object_r : httpd_sys_content_t : s0, 
Тип httpd_sys_content_t позволяет получить доступ к файлу, если мы обращаемся к нему через браузер.

13.  Изменила контекст файла /var/www/html/test.html с httpd_sys_content_t на samba_share_t: (рис. -@fig:008):

![Изменение контекста](im/8.PNG){ #fig:008 }

14. Попробовала ещё раз получить доступ к файлу через веб-сервер, введя в браузере адрес 
http://127.0.0.1/test.html  (рис. -@fig:009):

![Доступ к файлу через веб-браузер](im/9.PNG){ #fig:009 }

15. Файл не был отображен из-за того, что несмотря на возможность у любого пользователя просматривать файл, политика SELinux не задает правило, которое разрешало бы доступ, и операция сразу блокируется.
Посмотрю log-файлы веб-сервера Apache и системный log файл (рис. -@fig:010):

![log-файлы веб-сервера Apache и системный log файл](im/10.PNG){ #fig:010 }

В системном log файле указано, что моя система слишком медленная, поэтому посмотрю ошибки в файле /var/log/audit/audit.log (рис. -@fig:011):

![ошибки в файле audit.log](im/11.PNG){ #fig:011 }

Сравнить ошибки не получилось из-за ошибки в чтении системного лог файла.
 
16.  Попробовала запустить веб-сервер Apache на прослушивание ТСР-порта 81. 
Для этого в файле /etc/httpd/httpd.conf найду строчку Listen 80 и заменю 80 на 81 (рис. -@fig:012):

![Смена порта](im/12.PNG){ #fig:012 }

17.  Выполнила перезапуск веб-сервера Apache.
У меня сбоев не произошло. Возможно, это связано с тем, что данный порт зарезервирован и определен. Заменила 81 на 82. (рис. -@fig:013):

![Перезапуск веб-сервера](im/13.PNG){ #fig:013 }

Сбой произошел из-за того, что порт 82 не определен.

18. Проанализировала log файлы  /var/log/messages (рис. -@fig:014):

![log файлы /var/log/messages](im/14.PNG){ #fig:014 }

Снова ошибка, но я поискала информацию и определила, что подключение оборвалось, поскольку нет доступных сокетов и не получилось подключиться к адресу 0.0.0.82.

Просмотрела файл /var/log/http/error_log: (рис. -@fig:015):

![Файл error_log](im/15.PNG){ #fig:015 }

Просмотрю файл /var/log/audit/audit.log: (рис. -@fig:016):

![Файл audit.log](im/16.PNG){ #fig:016 }

Новых сообщений не появилось.

19. Выполнила команду semanage port -a -t http_port_t -р tcp 82: 
После этого проверила список портов командой 
semanage port -l | grep http_port_t:
20. Попробовала запустить веб-сервер Apache ещё раз. В этот раз запустить сервер получилось, поскольку на предыдущем шаге мы привязали новый порт. 
21.  Вернула контекст httpd_sys_cоntent__t к файлу /var/www/html/ test.html:

Действия пунктов 19-21 представленны на (рис. -@fig:017):

![Пункты 19-21](im/17.PNG){ #fig:017 }

Попробовала получить доступ к файлу /var/www/html/ test.html через браузер (рис. -@fig:018):

![Доступ к файлу через веб-браузер](im/18.PNG){ #fig:018 }

22.  Исправила обратно конфигурационный файл apache, вернув Listen 80 (рис. -@fig:019):

![Вернула конфиг. файл в первоначальное состояние](im/19.PNG){ #fig:019 }

23. Удалила привязку http_port_t к 82 порту
24. Удалила файл /var/www/html/test.html

Действия пунктов 23-24 представленны на (рис. -@fig:020):

![Пункты 23-24](im/20.PNG){ #fig:020 }

# Выводы

Развила навыки администрирования ОС Linux. Получила первое практическое знакомство с технологией SELinux. Проверила работу SELinx на практике совместно с веб-сервером Apache.
