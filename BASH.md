# ДИРЕКТОРИИ/КАТАЛОГИ
`cd -` возврат в предыдущую директорию после ее смены



### Очистить (удалить) содержимого файла
`echo -n path/file`

`cp /dev/null path/file`

`cat /dev/null path/file`

### Свободное место на диск
`df -h`

# Поиск
### Поиск файла по имени my.cnf
`sudo find / -name my.cnf`

# Копирование
#### файла на удаленный сервер
`scp ~/Downloads/file.txt root@123.123.123.123:~/Downloads/`

#### с удаленного сервера
`scp user@remote.host:file.txt /some/local/directory`

### Время на сервере
```
timedatectl # показать время
timedatectl list-timezones # показать доступные временные зоны
timedatectl set-timezone Asia/Yekaterinburg # установить временную зону
```

# Работа со строками
переместиться в начало строки `ctrl+a`

переместиться в конец строки `ctrl+e`
