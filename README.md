# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Викулов Александр`

### Задание 1

Процесс выполнения

1. Создадим два хоста в Yandex.Cloud

  * Первый хост: vikulov-vm-for-zabbix-server
    На эту машину будем устанавливать Zabbix сервер
  * Второй хост: vikulov-vm-for-zabbix-agent
    На эту машину будем устанавливать Zabbix агент
    
  Обе машины с абсолютно одинаковыми конфигурациями, на борту Debian 11, находятся в одной подсети
  
  Внутренние IP адреса присвоены облаком Яндекс автоматически:
  
  * `vikulov-vm-for-zabbix-server: 192.168.0.3`
  * `vikulov-vm-for-zabbix-agent-linux: 192.168.0.34`
  
  <p></p>
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img01.png">
  </kbd>
  <p></p> 

2. Подключимся к машине, на которой будем устанавливать Zabbix сервер

  <p></p>
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img02.png">
  </kbd>
  <p></p> 

3. Выберем конфигурацию Zabbix аналогично той, чтобы была в лекции

   * `Версия:      6.0 LTS`
   * `Дистрибутив: Debian 11`
   * `Компоненты:  Server Frontend Agent`
   * `База данных: PostgreSQL`
   * `Веб-сервер:  Apache`
  
  <p></p> 
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img03.png">
  </kbd>
  <p></p> 

4. Установим репозиторий Zabbix

   * Получим пакет с репозиторием
  
  <p></p>
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img04-1.png">
  </kbd>
  <p></p> 
   
   * Распакуем
  
  <p></p>
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img04-2.png">
  </kbd> 
  <p></p>
   
   * Обновим менеджер пакетов
  
  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img04-3.png">
  </kbd>
  <p></p>

5. Установим сервер и веб-интерфейс. Агент пока не устанавливаем.

  <p></p>
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img05.png">
  </kbd>
  <p></p>

6. Установим базу данных PostgreSQL

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master//img/task01-img06.png">
  </kbd>
  <p></p>

7. Создадим пользователя

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master//img/task01-img07.png">
  </kbd>
  <p></p>

8. Создадим базу данных

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img08.png">
  </kbd>
  <p></p>

9. Импортируем начальную схему и данные

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img09.png">
  </kbd>
  <p></p>

10. Отредактируем конфигурационный файл Zabbix, добавив туда пароль для СУБД (на скриншоте скрыт)

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img10.png">
  </kbd>
  <p></p>
  
11. Запустим Zabbix сервер и Apache сервер. Настроем их запуск при загрузке ВМ

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img11.png">
  </kbd>
  <p></p>
  
12. Переходим на хост и видим меню настройки Zabbix Frontend

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img12.png">
  </kbd>
  <p></p>

13. Настраиваем фронтенд и авторизируемся

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img13.png">
  </kbd>
  <p></p>

14. Попадаем в админку Zabbix

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img14.png">
  </kbd>
  <p></p>
    
---

<p></p>

### Задание 2

Процесс выполнения

1. Вернемся на страницу конфигурации и выберем теперь установку только агента.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img01.png">
  </kbd>
  <p></p>

2. Репозиторий Zabbix уже был настроен, поэтому пропустим этот пункт и перейдем к установке Zabbix агента.
   Вначале установим Zabbix агент на ту же машину, на которой расположен Zabbix сервер.
   
  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img02.png">
  </kbd>
  <p></p>

3. Запустим Zabbix агент и настроем его запуск при загрузке системы.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img03.png">
  </kbd>
  <p></p>

4. Увидим, что статус хоста Zabbix Server поменялся на Available.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img04.png">
  </kbd>
  <p></p> 

5. Перейдем к установки Zabbix агента на вторую машину.
   Для этого сначала настроим там Zabbix репозиторий как в задании 1 пункт 4
   
   * Скачаем файл с репозиторием
   
  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img05-1.png">
  </kbd>
  <p></p>
   
   * Распакуем

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img05-2.png">
  </kbd>
  <p></p> 
   
   * Обновим менеджер пакетов
   
  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img05-3.png">
  </kbd>
  <p></p> 

6. Установим Zabbix агент на вторую машину

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img06.png">
  </kbd>
  <p></p> 

7. Запустим Zabbix агент и настроем его запуск при загрузке системы.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img07.png">
  </kbd>
  <p></p> 

8. Теперь необходимо подключится к этой машине с нашего Zabbix сервера через админку. 
   Создадим новый хост и введем требуемые параметры. Подключаться будем по IP адресу внутренней подсети.
   
  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img08.png">
  </kbd>
  <p></p>

9. Видим, что сервер появился в списке, но пока недоступен.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img09.png">
  </kbd>
  <p></p>


10. Настроим агент на хост, на котором установлен Zabbix сервер.
    Для этого отредактируем конфигурационный файл на стороне агента. Добавим туда IP адрес нашего сервера.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img10.png">
  </kbd>
  <p></p> 
    
11. Теперь в админке настроем шаблон, по которому будут опрашиваться данные.
    Выберем стандартный шаблон Linux by Zabbix agent

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img11.png">
  </kbd>
  <p></p>

12. Увидим, что статус второго хоста изменился, и он начал мониторится сервером.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img12.png">
  </kbd>
  <p></p>

13. Через Latest Data проверим, что информация идет от агентов на обеих машинах.

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task02-img13.png">
  </kbd>
  <p></p>

---

## Дополнительные задания (со звездочкой*)

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

### Задание 3

К сожалению, нет физической возможности установить Zabbix агент на Windows.
Но, все равно, я попробую описать, что бы я делал в случае, если бы решал такую задачу. 

1. Для начала необходимо было бы поднять машину с Windows в той же сети, что и предыдущие две ВМ.
   В Yandex.Cloud нет возможности создать ВМ с Windows на борту, поэтому машина с Windows должна быть поднята на виртуалке, либо на железе.
   Это означает, что две машины в Yandex.Cloud и новая с Windows окажутся в разных сетях.
   Поэтому первое что надо будет сделать - это создать новую виртуальную сеть, в которой окажутся эти три машины.
   В новой вирутальной сети IP адреса машин поменяются, и для того, что сохранить данные предыдущего мониторинга с Linux машин, в админке надо будет вбить новые IP для хостов.

2. Далее скачем Zabbix агент для Windows

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task03-img02.png">
  </kbd>
  <p></p>

3. Запустим исполняемый файл. Установим Zabbix агент.
   Запустим Zabbix агент вбив в командную строку:
   `zabbix_agentd.exe --start`

4. Далее внесем IP адрес Zabbix сервера в конфигурационный файл.
   Файл должен будет находится по адресу `C:\zabbix_agentd.conf`
   После этого перезапустим Zabbix agent командами:
   `zabbix_agentd.exe --stop`
   `zabbix_agentd.exe --start`

5. Далее создадим новый хост в админке.
   Для него выберем темплейт Windows by Zabbix agent

  <p></p>
  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task03-img05.png">
  </kbd>
  <p></p>

6. После проделанных шагов по идеи всё должно заработать.


