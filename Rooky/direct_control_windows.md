# Прямое управление Rooky на Windows
## Подготовка
* Установить [git](https://git-scm.com/download/win)
* Установить [Python 3.5.4](https://www.python.org/ftp/python/3.5.4/python-3.5.4-amd64.exe) (При установке поставить галочку **"Add Python 3.5 to PATH"**)
* **Создать и перейти** в папку где будут храниться клонированные репозитории (например: C:\git)
* Нажать **Shift + правая кнопка мыши**
* Выбрать **Открыть окно PowerShell здесь**
* Клонировать репозиторий Rooky командой:
```bash
git clone https://github.com/Promobot-education/Rooky.git
```
* Перейти в папку с установочным скриптом командой:
```bash
cd .\Rooky\python
```
* Запустить скрипт установки библиотек командой:
```bash
python.exe setup.py install
```
* Установить [драйвера](/Rooky/res/drivers/CDM21228_Setup.exe) для интерфейсной платы
* **Настройка закончена**

## Запуск примеров Python

* Запустить программу **IDLE (Python 3.5)**(находится в меню Пуск)
* Открыть файл arm_test.py (**Ctrl + O**) из папки **Rooky\python\examples**
* Заменить порт на соответствующий порт подключенной интерфейсной платы, например: 
  
  ``arm = Rooky.Rooky('COM2','left')``
* Запустить модуль (**F5**)

## Запуск примеров на языке С++ (на примере компилятора MinGW)
1. Установить компилятор С++
   при использовании MinGW необходимо:
   - установить [mingw-get-setup](https://sourceforge.net/projects/mingw/files/latest/download)
   - после установки автоматически запустится MinGW Installation Manager (ярлык MinGW Installer на рабочем столе)
   - отметить **mingw-developer-toolkit, msys-base, mingw32-base, g++** для установки
   - нажать **Installation -> Apply changes -> Apply**
   - нажать **Win + R**
   - и ввести **SystemPropertiesAdvanced.exe**
   - нажать **"Переменные среды"**
   - выбрать Path и нажать **"Изменить"**
   - нажать "Обзор" и указать путь до папки **bin** куда установлен MinGW (например C:\MinGW\bin)
   - также еще указать путь до папки **msys\1.0\bin** (например C:\MinGW\msys\1.0\bin)
   - везде нажать "OK"
   - проверить что всё работает:
     - нажать **Win + X**
     - запустить **PowerShell** (без прав администратора)
     - ввести команду: ``g++ --version`` 
     - должна отобразиться версия компилятора g++
2. Скачать библиотеку [libmodbus](https://github.com/stephane/libmodbus/archive/refs/tags/v3.1.6.zip)
3. Распаковать библиотеку на диск ``С:\``
4. Зайти в папку **C:\libmodbus-3.1.6**
5. Нажать **Shift + правая кнопка мыши**
6. Выбрать **Открыть окно PowerShell здесь**
7. Подать следующие команды:
   ```PowerShell
   sh
   ./autogen.sh
   ./configure --prefix=/usr/local/
   cd src
   make install
   ```
   * закрыть PowerShell
8. Открыть файл с примером, например файл **Rooky\cpp\examples\read_servos.cpp**
9. В файле заменить имя COM порта ``"/dev/RS_485"`` в строке ``initRooky("/dev/RS_485", side, false)``  
   на COM порт подключенной интерфейсной платы, например ``initRooky("COM3", side, false)``, **сохранить**
10. Вернуться в папку с библиотекой для языка **С++** (Путь: Rooky\cpp)
11. Нажать **Shift + правая кнопка мыши**
12. Выбрать **Открыть окно PowerShell здесь**
13. Скомпилировать исходный код примеров, подав команды
    ```PowerShell
    sh
    make
    ```
14. Скопировать файл "libmodbus-5.dll" из **C:\MinGW\msys\1.0\local\bin** в папку **Rooky\cpp\build**
15. Запустить **read_servos.exe** в папке **Rooky\cpp\build**
16. **Гордиться собой!!!**