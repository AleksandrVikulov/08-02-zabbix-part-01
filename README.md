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
    <img src="ttps://github.com/AleksandrVikulov/08-02-zabbix-part-01/blob/master/img/task01-img05.png">
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

`Процесс выполнения`

1. ``

2. ``

3. ``

4. ``

5. ``

6. ``

7. ``

8. ``

9. ``

10. ``

---
## Дополнительные задания (со звездочкой*)

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

### Задание 3

1. ``

2. ``

3. ``

4. ``

5. ``

6. ``

7. ``

8. ``

9. ``

10. ``

