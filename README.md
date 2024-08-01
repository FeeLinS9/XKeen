# Настройка Keenetic для XKeen
## Подготовка USB накопителя
### Использование файловой системы EXT4 на USB-накопителях.
Для работы накопителей с файловой системой EXT4 в роутере Keenetic предварительно нужно установить компонент "Файловая система Ext". Сделать это можно на странице "Общие настройки" в разделе "Обновления и компоненты", нажав на "Изменить набор компонентов".
![image](https://github.com/FeeLinS9/XKeen/blob/master/8.png)\

### Форматируем накопитель в Ext4.
#### Форматирование в Linux:
Универсальным способом форматирования USB-накопителя является использование утилиты для управления дисками GParted. Обычно она уже установлена в ОС, но при необходимости её можно установить из официальных репозиториев (выполните sudo apt install gparted или sudo yum install gparted в зависимости от дистрибутива).

Запустите GParted. В правом верхнем углу выберите нужное устройство (идентифицировать свой накопитель можно по метке, размеру или файловой системе). Размонтируйте накопитель, чтобы появилась возможность форматирования.\
![image](https://github.com/FeeLinS9/XKeen/blob/master/1.png)\
![image](https://github.com/FeeLinS9/XKeen/blob/master/2.png)\
![image](https://github.com/FeeLinS9/XKeen/blob/master/3.png)\
\
Также форматирование можно выполнить специальными командами через Терминал.

Один из способов следующий:

Выполните команду df и определите раздел подключенного накопителя (/dev/sdb, /dev/sdc, ...). Предположим, что в нашем примере флэшка находится в /dev/sdc1.

Далее её следует отмонтировать. Сделать это можно командой:
```
sudo umount /dev/sdc1
```
Теперь, для форматирования её в файловую систему ext4 с меткой "USB", выполните команду:
```
sudo mkfs.ext4 -n 'USB' -I /dev/sdc1
```

#### Форматирование в Windows:
 Можно воспользоваться бесплатной версией программы Paragon Partition Manager Free или AOMEI Partition Assistant Standard Edition.\
Приведем пример форматирования накопителя в MiniTool Partition Wizard Free Edition:\
![image](https://github.com/FeeLinS9/XKeen/blob/master/4.jpg)\
![image](https://github.com/FeeLinS9/XKeen/blob/master/5.jpg)\
![image](https://github.com/FeeLinS9/XKeen/blob/master/6.jpg)\
![image](https://github.com/FeeLinS9/XKeen/blob/master/7.jpg)\
Подключите подготовленный диск с файловой системой EXT4 к маршрутизатору в USB-порт. Диск должен появиться в меню 'Приложения' на странице 'USB-устройства'.\
![image](https://github.com/FeeLinS9/XKeen/blob/master/9.png)\