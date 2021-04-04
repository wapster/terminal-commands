# Содержание
* [Google Chrome](../main/commands.md#google-chrome)
* [Composer](../main/commands.md#composer)
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
> `sudo apt-get purge chromium-browser`

---
# Composer
Обновление
> `php composer.phar self-update`

Обновление до 2й ветки

> #### `composer self-update --2`

---
