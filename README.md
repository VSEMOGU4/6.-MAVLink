Задание № 6. Разработать алгоритм по заданным маршрута с применением протокола MAVLink.

Шаг 1. Изучил техническую документацию к протоколу MAVLink версии 2.0 - структуры данных, форматы пакетов, систему команд.
 
 

Структура пакета MAVLink имеет следующий формат:

- STX — символ начала сообщения.

- LEN — длина полезной нагрузки.

- SEQ — счётчик пакета.

- SYS — идентификатор отправляющей системы.

- COMP — идентификатор отправляющего компонента.

- MSG — тип сообщения.

- PAYLOAD — полезная нагрузка пакета.

- CKA и CKB — нижний и верхний байт, соответственно, содержат контрольную сумму пакета.
Система команд: 
Примеры MAVLink-сообщений:

ATTITUDE, ATTITUDE_QUATERNION — ориентация квадрокоптера в пространстве.

LOCAL_POSITION_NED — локальная позиция квадрокоптера.

GLOBAL_POSITION_INT — глобальная позиция квадрокоптера (широта, долгота, высота).

COMMAND_LONG — команда для квадрокоптера 
MAV_CMD_NAV_WAYPOINT
mode GUIDED 
mode RTL 
mode AUTO 
takeoff 10  - высота
position x y z
arm throttle 
setyaw 50 50 0 
param show WPNAV_SPEED
param set WPNAV_SPEED 200
и т.д.

Шаг 2. Определил координаты начальной, конечной и промежуточных точек маршрута. Задал параметры - макс. высота, скорость.

 





Шаг 3. Спроектировал алгоритм расчета оптимального маршрута между заданными точками.

 
Шаг 4. Реализовал алгоритм на языке Python с применением библиотеки pymavlink.
 

Шаг 5. Протестировал алгоритм в симуляторе ArduPilot или Mission Planner.

 

