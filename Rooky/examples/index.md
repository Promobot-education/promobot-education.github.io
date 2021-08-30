# Описание библиотек и примеров работы с Rooky
В данном разделе дано описание для файлов с примерами кода, который использует прилагаемые библиотеки на языках C и Python.

## Python

#### Описание библиотеки прямого управления Rooky

ℹ️ [Rooky](/Rooky/libs/python/Rooky) - высокий уровень абстракции - работа с суставами.  
> Запуск примеров производить через python версии не ниже 3.5 (например командой python3 arm_test.py)

ℹ️ [Rooky2](/Rooky/libs/python/Rooky2) - Вторая версия библиотеки, совместимая с Python интерпретатором в RRStudio.  
> Запуск примеров производить через python версии не ниже 3.5 (например командой python3 arm_test_2.py)

ℹ️ [Servo_ppm](/Rooky/libs/python/Servo_ppm) - Библиотека для работы с ppm платой (сервоприводы кисти и пальцев, датчик касания).

#### Примеры прямого управления
* [arm_test](/Rooky/examples/python/arm_test) - Движение суставами на указанный угол.
* [arm_test_2](/Rooky/examples/python/arm_test_2) - Пример использования второй версии библиотек.
* [read_touch](/Rooky/examples/python/read_touch) - Получение данных от датчика касания.

#### Примеры работы через узел ROS
* [move_joints](/Rooky/examples/python/ros/move_joints) - Движение суставами на указанный угол.

## C++

#### Описание библиотеки прямого управления Rooky

ℹ️ [Rooky](/Rooky/libs/cpp/Rooky) - высокий уровень абстракции - работа с суставами.

ℹ️ [Servo](/Rooky/libs/cpp/Servo) - средний уровень абстракции - работа с сервоприводами и датчиком касания.

ℹ️ [bus_handler](/Rooky/libs/cpp/bus_handler) - низкий уровень абстракции - работа с последовательным портом.

#### Примеры прямого управления
* [move_joints](/Rooky/examples/cpp/move_joints) - Движение суставами на указанный угол.
* [read_servos](/Rooky/examples/cpp/read_servos) - Цикличное считывание данных с сервоприводов и датчика касания.

#### Примеры работы через узел ROS
* [move_joints](/Rooky/examples/cpp/ros/move_joints) - Движение суставами на указанный угол.
* [read_touch](/Rooky/examples/cpp/ros/read_touch) - Цикличное считывание данных с датчика касания.