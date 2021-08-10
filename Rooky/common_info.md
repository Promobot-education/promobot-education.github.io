# Общая информация

>Внимание. При работе с манипулятором Rooky через ROS, рекомендуется обеспечить отдельный компьютер с Linux Ubuntu 16 в качестве основной операционной системы.  

<div style="width: 100%; height: 50px; padding:0px 0px 0px 20px; float:left;">
    <a href="https://cdimage.ubuntu.com/ubuntu-gnome/releases/16.04/release/"> 
        <img src="/Rooky/res/ubuntu.png" height="40px" align="left" alt="ubuntu">
    </a>
    <div style="width: 80%; margin:9px 20px; height:20px;">
        <a href="https://cdimage.ubuntu.com/ubuntu-gnome/releases/16.04/release/" style="margin-left:2px; align:left;">Скачать Ubuntu 16.04 LTS для установки в качестве основной ОС</a>
    </div>
</div>

>Внимание.  
>ПО сервоприводов в Rooky имеет ограничение на удержание положения!  
>Сервоприводы способны удерживать позицию примерно полторы минуты, после чего произойдет отключение.  
>Нормальной работой, при которой не будет происходить отключение, считается подъем и опускание суставов, без длительного удержания положения.

Для работы напрямую с подключенным по USB устройством **Rooky** используются библиотеки на языках программирования **C++** и **Python**.

Протокол взаимодействия с устройством - **MODBUS RTU**.

Библиотеки основаны на существующих решениях для работы с протоколом MODBUS:
* [modbus-tk](https://github.com/ljean/modbus-tk) (Python)
* [libmodbus](https://github.com/stephane/libmodbus) (C++)

Интерфейс работы с устройством на шине - **RS485**.

Структура работы с устройством Rooky:

![device_image](/Rooky/res/edu.png "Struct")