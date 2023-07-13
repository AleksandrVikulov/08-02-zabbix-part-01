# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Викулов Александр`

### Задание 1

`Процесс выполнения`

1. `Создадим два хоста в Yandex.Cloud`

  * `Первый хост: vikulov-vm-for-zabbix-server`
    `На эту машину будем устанавливать Zabbix сервер`
  * `Второй хост: vikulov-vm-for-zabbix-agent`
    `На эту машину будем устанавливать Zabbix агент`
    
  `Обе машины с абсолютно одинаковыми конфигурациями, на борту Debian 11, находятся в одной подсети`
  
  `Внутренние IP адреса присвоены облаком Яндекс автоматически:`
  
  * `vikulov-vm-for-zabbix-server: 192.168.0.3`
  * `vikulov-vm-for-zabbix-agent-linux: 192.168.0.34`
  
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/img/task01_img01.png">
  </kbd> 

2. `Подключимся к машине, на которой будем устанавливать Zabbix сервер`

  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/img/task01_img02.png">
  </kbd> 

3. `Выберем конфигурацию Zabbix аналогично той, чтобы была в лекции`

   * `Версия:      6.0 LTS`
   * `Дистрибутив: Debian 11`
   * `Компоненты:  Server Frontend Agent`
   * `База данных: PostgreSQL`
   * `Веб-сервер:  Apache`
   
  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/img/task01_img03.png">
  </kbd> 

4. `Установим репозиторий Zabbix`

   * `Получим пакет с репозиторием`

  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/master/img/task01_img04-1.png">
  </kbd> 
   
   * `Распакуем`

  <kbd> 
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/master/img/task01_img04-2.png">
  </kbd> 
   
   * `Обновим менеджер пакетов` 

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img04-3.png">
  </kbd>

5. `Установим сервер и веб-интерфейс. Агент пока не устанавливаем.`

  <kbd> 
    <img src="AleksandrVikulov.io/08-02-zabbix-part-01/img/task01_img05.png">
  </kbd>

6. `Установим базу данных PostgreSQL`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img06.png">
  </kbd>

7. `Создадим пользователя`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img07.png">
  </kbd>

8. `Создадим базу данных`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img08.png">
  </kbd>

9. `Импортируем начальную схему и данные`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img09.png">
  </kbd>

10. `Отредактируем конфигурационный файл Zabbix, добавив туда пароль для СУБД (на скриншоте скрыт)`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img10.png">
  </kbd>
  
11. `Запустим Zabbix сервер и Apache сервер. Настроем их запуск при загрузке ВМ`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img11.png">
  </kbd>
  
12. `Переходим на хост и видим меню настройки Zabbix Frontend`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img12.png">
  </kbd>

13. `Настраиваем фронтенд и авторизируемся`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img13.png">
  </kbd>

14. `Попадаем в админку Zabbix`

  <kbd>
    <img src="https://github.com/AleksandrVikulov/08-02-zabbix-part-01/raw/main/img/task01_img14.png">
  </kbd>
    

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

