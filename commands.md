# Содержание
* [Git](../main/commands.md#git)
* [Google Chrome](../main/commands.md#google-chrome)
* [Composer](../main/commands.md#composer)
* [MySQL](../main/commands.md#mysql)
---
# Команды
### Копирование файла на удаленный сервер
> `scp ~/Downloads/file.txt root@123.123.123.123:~/Downloads/`


### Время на сервере
> `timedatectl` # показать время
> `timedatectl list-timezones` # показать доступные временные зоны
> `timedatectl set-timezone Asia/Yekaterinburg` # установить временную зону

---
# Git
Добавить изменения к последнему коммиту
> `git commit -a --amend`

Просмотр удаленных репозиториев
> `git remote -v`
---
# Google Chrome

#### Установка
скачиваем и распаковываем DEB пакет:
> `wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb`

> `sudo dpkg -i google-chrome-stable_current_amd64.deb`

> `whereis google-chrome`

#### Обновление 
> `google-chrome-stable -version`

> `sudo apt-get upgrade google-chrome-stable`

#### Удаление
> `$ sudo apt-get purge google-chrome-stable`
> `$ rm ~/.config/google-chrome/ -rf`
> `$ rm ~/.cache/google-chrome/ -rf`
Вы также можете удалить `/etc/apt/sources.d/google.list` и его открытые ключи, которые были добавлены в `/etc/apt/trusted.gpg`.

---
# Chromium

### Установка
Без snap
> `https://itectec.com/ubuntu/ubuntu-chromium-without-snap/`

### Удаление

Как snap пакет
> `snap remove chromium`
> `sudo apt purge chromium-browser chromium-chromedriver`

---
# Composer
Обновление
> `php composer.phar self-update`

Обновление до 2й ветки

> `composer self-update --2`

---
# MySQL
### Установка
> `sudo apt-get install mysql-server`

Статус: остановить, запустить, проверить
> `systemctl stop mysql.service`
> `systemctl start mysql.service`
> `systemctl status mysql.service`

### Настройка
Файл конфигурации, в котором хранятся логин и пароль
> `sudo nano /etc/dbconfig-common/phpmyadmin.conf`
dbc_dbuser='your_username'
dbc_dbpass='your_password'

### Команды для работы c MySQL
Вход
> `shell> sudo mysql -u user_name -p`
> `Enter password: ********`

Выход
> `mysql> QUIT`
> `Control-D`

Показать всех пользователей
> `mysql> SELECT user FROM mysql.user;`

Создать пользователя (от имени пользователя root)
> `CREATE USER 'user_name'@'host' IDENTIFIED BY 'password';`

Назначить права доступа пользователю (от имени пользователя root)
> `GRANT ALL PRIVILEGES ON * . * TO 'user_name'@'host';`
> `FLUSH PRIVILEGES;` # чтобы изменения вступли в силу

Отменить определенные привилегии пользователя
> `REVOKE ALL PRIVILEGES ON db_name.table_name FROM 'user_name'@'localhost';`

Просмотр прав доступа пользователя
> `SHOW GRANTS FOR 'user_name'@'localhost';`

Удалить существующую учётную запись пользователя
> `DROP USER 'user_name'@'localhost';`
