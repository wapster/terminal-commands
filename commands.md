# Содержание
* [Команды](../main/commands.md#команды)
* [Git](../main/commands.md#git)
* [Composer](../main/commands.md#composer)
* [PHPUnit](../main/commands.md#phpunit)
* [MySQL](../main/commands.md#mysql)
* [BASH Aliases](../main/commands.md#bash_aliases)
* [Google Chrome](../main/commands.md#google-chrome)
---
# Команды

### Очистить (удалить) содержимого файла
> `echo -n > path/file`

> `cp /dev/null path/file`

> `cat /dev/null > path/file`

### Свободное место на диск
> `df -h`

### Поиск файла по имени my.cnf
> `sudo find / -name my.cnf`

### Копирование файла на удаленный сервер
> `scp ~/Downloads/file.txt root@123.123.123.123:~/Downloads/`

### Копирование с удаленного сервера
> `scp user@remote.host:file.txt /some/local/directory`

### Время на сервере
> `timedatectl` # показать время

> `timedatectl list-timezones` # показать доступные временные зоны

> `timedatectl set-timezone Asia/Yekaterinburg` # установить временную зону

---
# Git
* Добавить изменения к последнему коммиту
> `git commit -a --amend`

* Просмотр удаленных репозиториев
> `git remote -v`
---

# PHPUnit
### Глобальная установка
> `wget -O phpunit https://phar.phpunit.de/phpunit-9.phar`

> `chmod +x phpunit.phar`

> `sudo mv phpunit.phar /usr/local/bin/phpunit`

> `phpunit --version`

### Установка через Composer
> `php composer.phar require --dev phpunit/phpunit ^9`

### Проверить версию
> `php ./vendor/bin/phpunit --version`
---
# Google Chrome

#### Установка
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

Вы также можете удалить `/etc/apt/sources.d/google.list` и его открытые ключи, 
которые были добавлены в `/etc/apt/trusted.gpg`.

---
# Chromium

### Установка
* Без snap
> `https://itectec.com/ubuntu/ubuntu-chromium-without-snap/`

### Удаление

* Как snap пакет
> `snap remove chromium`
> `sudo apt purge chromium-browser chromium-chromedriver`

---
# Composer
### Установка
> `php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"`

> `php -r "if (hash_file('sha384', 'composer-setup.php') ===` > ` '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"`

> `php composer-setup.php`

> `php -r "unlink('composer-setup.php');"`

### Обновление
> `php composer.phar self-update`

* Обновление до 2й ветки

> `composer self-update --2`

---
# MySQL
### Установка
> `sudo apt-get install mysql-server`

### Статус: остановить, запустить, проверить, перезапустить
> `systemctl stop mysql.service`

> `systemctl start mysql.service`

> `systemctl status mysql.service`

> `/etc/init.d/mysql restart`

### Настройка
* Файл конфигурации, в котором хранятся логин и пароль
> `sudo nano /etc/dbconfig-common/phpmyadmin.conf`
dbc_dbuser='your_username'
dbc_dbpass='your_password'

* узнать какой файл конфигурации читает сервер MySQL
> `which mysqld`

> `# /usr/sbin/mysqld`

> `/usr/sbin/mysqld --verbose --help | grep -A 1 'Default options'`

> `# Default options are read from the following files in the given order:`

> `# /etc/my.cnf /etc/mysql/my.cnf ~/.my.cnf`

### Команды для работы c MySQL
* Вход
> `shell> sudo mysql -u user_name -p`

> `Enter password: ********`

* Выход
> `mysql> QUIT`

> `Control-D`

* Показать всех пользователей
> `mysql> SELECT user FROM mysql.user;`

* Создать пользователя (от имени пользователя root)
> `CREATE USER 'user_name'@'host' IDENTIFIED BY 'password';`

* Назначить права доступа пользователю (от имени пользователя root)
> `GRANT ALL PRIVILEGES ON * . * TO 'user_name'@'host';`

> `FLUSH PRIVILEGES;` # чтобы изменения вступли в силу

* Отменить определенные привилегии пользователя
> `REVOKE ALL PRIVILEGES ON db_name.table_name FROM 'user_name'@'localhost';`

* Просмотр прав доступа пользователя
> `SHOW GRANTS FOR 'user_name'@'localhost';`

* Удалить существующую учётную запись пользователя
> `DROP USER 'user_name'@'localhost';`

---
# BASH ALIASES (~/.bash_aliases)
### [Общие команды]
> `alias c='clear'`

> `alias nano='nano -l'`

> `alias ll='ls -alF --color=auto'`

> `alias setal='nano ~/.bash_aliases'`

> `alias saveal='source ~/.bash_aliases'`

> `alias clearfile='echo -n >'`

### [MySQL]
> `alias mysqlstart='sudo systemctl start mysql.service'`

> `alias mysqlstop='sudo systemctl stop mysql.service'`

> `alias mysqlrestart='sudo /etc/init.d/mysql restart'`

> `alias mysqlstatus='sudo systemctl status mysql.service'`