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
