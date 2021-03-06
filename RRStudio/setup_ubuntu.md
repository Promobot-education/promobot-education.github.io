# Установка и запуск RRStudio на Ubuntu 16.04
## Установка
#### Вариант №1, рекомендуемый (использование ppa):
* Открыть терминал (**Ctrl + Alt + T**)
* Добавить в систему ppa репозиторий (если не добавлен) командой:
  ```sh
  curl -s --compressed "https://Promobot-education.github.io/ppa/KEY.gpg" | sudo apt-key add -
  sudo curl -s -o /etc/apt/sources.list.d/promobot-education.list "https://Promobot-education.github.io/ppa/promobot-education.list"
  ```
* Установить пакет:
  ```sh
  sudo apt update
  sudo apt install promobot-rrstudio
  ```

#### Вариант №2:
* Вручную скачать **deb** пакет "[promobot-rrstudio](https://github.com/promobot-education/RRStudio/releases)"
* Открыть пакет с помощью **"Установка приложений"**

или установить пакет с помощью команды: 

* Открыть директорию с **deb** пакетом
* Нажать правую кнопку мыши -> **Открыть терминал**
* Ввести команду:
```
sudo apt install ./promobot-rrstudio<...>.deb
```

## Запуск
* Запустить RRStudio из приложений
- Выбрать устройство 
- Подключиться:
  - напрямую к COM порту  
    или
  - по IP к серверу
  > если RRStudio и серверное ПО работают на одном компьютере  
  > в одной операционной системе, тогда IP адресс:  
  > ``127.0.0.1``

## Обновление
* Следовать [инструкции](https://github.com/Promobot-education/ppa/wiki) по обновлению из ppa репозитория