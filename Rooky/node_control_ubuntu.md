# Управление Rooky через узел ROS на Ubuntu 16.04
# Подготовка
* Открыть терминал: **Ctrl + Alt + T**
* Написать следующие команды:
  ```sh
  cd ~
  git clone https://github.com/Promobot-education/Rooky.git
  cd Rooky
  chmod +x ./install.sh
  ./install.sh
  ```
* Потребуется скачать ROS Kinetic ~2Gb
  ```sh
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  sudo apt install curl # Если curl не установлен
  curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
  sudo apt-get update
  sudo apt-get install ros-kinetic-desktop-full
  sudo apt install python-rosdep
  sudo rosdep init
  rosdep update
  echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
  source ~/.bashrc
  ```
* Установить пакет с серверным ПО **promobot-edu-control**
  * Добавить в систему ppa репозиторий (если не добавлен)
    ```sh
    curl -s --compressed "https://Promobot-education.github.io/ppa/KEY.gpg" | sudo apt-key add -
    sudo curl -s -o /etc/apt/sources.list.d/promobot-education.list "https://Promobot-education.github.io/ppa/promobot-education.list"
    ```
  * Установить пакет:
    ```sh
    sudo apt update
    sudo apt install promobot-edu-control
    ```
  * Добавить путь до файлов серверного ПО
    ```sh
    echo "source /opt/promobot/EduControl/install/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```
  * Проверить зависимости
    ```sh
    cd /opt/promobot/EduControl
    rosdep install --from-paths install --ignore-src -r -y
    ```
* **Подготовка для работы с узлом ROS закончена.**

# Запуск

## 1. Запуск серверного ПО для работы с реальным устройством
* Открыть терминал: **Ctrl + Alt + T**
* В зависимости от типа Rooky запустить ROS командой:
  * **Для левой Rooky:**
    ```sh
    roslaunch promobot_control promobot_hardware.launch side:=left
    ```
  * **Для правой Rooky:**
    ```sh
    roslaunch promobot_control promobot_hardware.launch side:=right
    ```
  * Запустить узел, инструкция ниже

С
#### Запуск узла ROS на языке Python
* Открыть еще один терминал: **Ctrl + Alt + T**
* Отредактировать файл **move_joints.py** в соответствии с типом Rooky:
  * ```sh
    nano ~/Rooky/ros/move_joints.py
    ```
  * ```py
    node = ControlJoints("left") # ControlJoints может принимать "left" или "right"
    ```
  * сохранить
    * **CTRL + X**
    * нажать **Y**
    * подтвердить название файла
* Подать команду для перехода в директорию с примером:
  ```sh
  cd ~/Rooky/ros/
  ```
* Запустить пример:
  ```
  python move_joints.py
  ```

#### Запуск узла ROS на языке C++
* Открыть еще один терминал: **Ctrl + Alt + T**
* Отредактировать файл **move_joints.cpp** в соответствии с типом Rooky:
  * ```sh
    nano ~/Rooky/ros/cpp_examples_ws/src/examples/src/move_joints.cpp
    ```
  * ```cpp
    RookySide rooky_side = LEFT; // rooky_side может принимать 2 значения: LEFT или RIGHT
    ```
  * сохранить
    * **CTRL + X**
    * нажать **Y**
    * подтвердить название файла
* Подать команду для перехода в директорию с workspace:
  ```sh
  cd ~/Rooky/ros/cpp_examples_ws
  ```
* Скомпилировать:
  ```sh
  catkin_make install
  ```
* Чтобы ROS знал где скомпилированный пакет "examples" - выполнить:
  ```sh
  source ~/Rooky/ros/cpp_examples_ws/install/setup.bash
  ```
* Запусить узел:
  ```sh
  rosrun examples move_joints
  ```

## Запуск серверного ПО для работы в режиме симуляции без реального устройства
Запуск симуляции происходит аналогично запуску с реальным устройством.  
Отличаются только команды на запуск серверного ПО (ROS):  
* **Для левой Rooky:**
  ```sh
  roslaunch promobot_control start_simulation.launch side:=left
  ```
* **Для правой Rooky:**
  ```sh
  roslaunch promobot_control start_simulation.launch side:=right
  ```