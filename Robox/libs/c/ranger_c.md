# Описание библиотеки Ranger.c 
***

### int trig_sensor(int addr)
    Старт измерения расстояния
    Args:
        addr - адрес устройства.
    Returns:
        *  0 если отправка команды прошла успешно
        * -1 если при отправке команды произошла ошибка

    
### struct sensor_data read_sensor(int addr):
    Чтение данных (измеренная дистанция) с датчика расстояния
    Args:
        addr - адрес устройства.
    Returns:
        Даныые с датчика расстояния. Структура servo_data с данными:
        struct sensor_data {
            uint8_t US_distance;
            uint8_t IR_distance;
        };
   
### int set_min_dist(int addr, int dist)
    Выставление порога измеренного расстояния, ниже которого загорается светодиод
    Args:
        * addr - адрес устройства.
        * dist - дистанция в мм.
    Returns:
        *  0 если отправка команды прошла успешно
        * -1 если при отправке команды произошла ошибка


