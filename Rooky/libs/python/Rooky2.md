# Библиотека для прмяой работы с Rooky.

```python
class Rooky():
    """Класс для работы с манипулятором.

    Args:
        * port (str): Имя посдеовательного порта манипулятора.
        * side (str): Типа манипулятора. Левый или правый.
        * debug (bool): Вывод отладочной информации в консоль.
    """  

    def __init__(self, port, side = "left", debug = False)


    def move_joints(self, joints, move_time):
        """Установка указанных суставов на указанные углы поворота
        Args:
            * joints - list(dict('name': , 'degree': )) список словарей с ключами:
                    name - имя сустава, например для правой Rooky 'name':'right_arm_1_joint'
                    degree - абсолютный угол(градусы) - угол относительно нулевого положения, 
                             на который нужно установить сустав
            * move_time - время, за которое суставы должны оказаться в итоговом месте
        Returns:
            None
        Raises:
            None
        """


    def read_servos_data(self):
        """Чтение доступных данных с сервоприводов
        Args:
            None
        Returns:
            * список словарей с информацией от сервоприводов.
            См Servo.get_data(), а также Servo_ppm.Main_ppm.get_data()
        Raises:
            None
        """


    def get_sensor_value(self):
        """Чтение данных с датчика касания
        Args:
            None
        Returns:
            * value (int) - безразмерная величина, при касании уменьшается
        Raises:
            None
        """


    def is_touched(self):
        """Есть ли факт касания датчика касания
        Args:
            None
        Returns:
            * True - есть касание датчика
              False - нет касания датчика
        """


    def reset_joints(self):
        """Сброс всех суставов в нулевое положение
        Args:
            None
        """


    def get_servo_angle(self, joint):
        """Получить положение сустава
        Args:
            * joint - имя сустава, например "right_arm_1_joint", 
                    допустимо передать номер сустава, например - 7
        Returns:
            * angle (float) - угол в котором сейчас находится сустав
        """


    def calibration(self):
        """Калибровка, в данном случае сброс суставов в начальное положение.
        Args:
            None
        """


    def set_touch_sensor_threshold(self, percent):
        """Установить чувствительность для определения факта касания
        Args:
            * percent - процент различий
                        чем меньше процент различий, 
                        тем выше программная чувствительность для регистрации касания
        """
```