# Трекер на Arduino Nano (однофайловый скетч)

Старая версия прошивки трекера одним файлом `AGLoRa-tracker.ino` для Arduino IDE: Arduino Nano или UNO (ATmega328P), LoRa EBYTE E220 или E32, GPS-модуль, Bluetooth-модуль AT-09 (HM-10).

Основная прошивка — проект PlatformIO в `full-stack`, для XIAO ESP32-C3 пользоваться ей.

## Подключение

LoRa:
```
Arduino     LoRa
Pin 2  ——>  TX
Pin 3  ——>  RX
Pin 4  ——>  M0
Pin 5  ——>  M1
Pin 6  ——>  AX
5V     ——>  VCC
GND    ——>  GND
```

GPS:
```
Arduino     GPS
Pin 7  ——>  TX
Pin 8  ——>  RX
5V     ——>  VCC
GND    ——>  GND
```

Bluetooth (по желанию):
```
Arduino         Bluetooth
RX (Pin 0) ——>  TX
TX (Pin 1) ——>  RX
5V         ——>  VCC
GND        ——>  GND
```

Для питания от батареи нужен стабилизатор 5 В (например, LM7805).

## Загрузка

1. Установить в Arduino IDE библиотеки «EByte LoRa E220» (или «LoRa E32») и «TinyGPSPlus».
2. Задать имя трекера `NAME`, выключить `DEBUG_MODE`. `NAME_LENGTH` должен быть одинаковым на всех трекерах.
3. Загрузить скетч. Перед включением к LoRa-модулю должна быть подключена антенна.

## Проверка модулей

В `hardware-tests/` два отдельных скетча: проверка GPS и проверка LoRa.
