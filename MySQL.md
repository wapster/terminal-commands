### Установка
`sudo apt-get install mysql-server`

### Статус: остановить, запустить, проверить, перезапустить
`systemctl stop mysql.service`

`systemctl start mysql.service`

`systemctl status mysql.service`

`/etc/init.d/mysql restart`

### Настройка
* Файл конфигурации, в котором хранятся логин и пароль
`sudo nano /etc/dbconfig-common/phpmyadmin.conf`
> dbc_dbuser='your_username'
> dbc_dbpass='your_password'

* узнать какой файл конфигурации читает сервер MySQL
`which mysqld`

`# /usr/sbin/mysqld`

`/usr/sbin/mysqld --verbose --help | grep -A 1 'Default options'`

`# Default options are read from the following files in the given order:`

`# /etc/my.cnf /etc/mysql/my.cnf ~/.my.cnf`

### Команды для работы c MySQL
* Вход
`shellsudo mysql -u user_name -p`

`Enter password: ********`

* Выход
`mysqlQUIT`

`Control-D`

* Показать всех пользователей
`mysqlSELECT user FROM mysql.user;`

* Создать пользователя (от имени пользователя root)
`CREATE USER 'user_name'@'host' IDENTIFIED BY 'password';`

* Назначить права доступа пользователю (от имени пользователя root)
`GRANT ALL PRIVILEGES ON * . * TO 'user_name'@'host';`

`FLUSH PRIVILEGES;` # чтобы изменения вступли в силу

* Отменить определенные привилегии пользователя
`REVOKE ALL PRIVILEGES ON db_name.table_name FROM 'user_name'@'localhost';`

* Просмотр прав доступа пользователя
`SHOW GRANTS FOR 'user_name'@'localhost';`

* Удалить существующую учётную запись пользователя
`DROP USER 'user_name'@'localhost';`
