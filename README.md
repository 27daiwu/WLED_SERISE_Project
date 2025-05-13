
# wled-json-api-over-serial
This is a very simple [example code](https://github.com/miwied/wled-json-api-over-serial/blob/main/src/main.cpp) of how to work with the [WLED](https://github.com/Aircoookie/WLED) json api over serial using [PlatformIO](https://platformio.org/) and the [ArduinoJson library](https://github.com/bblanchon/ArduinoJson).

With the help of the wled json api you are able to use all api commands to control a wled-flashed-mcu with any other serial capable microcontroller. 

In my example sketch by pressing a button which is conntected to the sending-mcu it will change the color of the led-strip on the wled-mcu.

## Setup:
- sending-µC: esp32 
- receiving-µC: esp32 with WLED0.15
- wled version: "WLED-0.15"
- baud rate: 115200 

## Note:
SoftwareSerial is only suitable for very slow baud rates, definitely not 921600. You should always use HardwareSerial if possible, and in case SoftwareSerial is indispensable, use the lowest possible rate.
本代码用HardwareSerial，波特率115200

## Connections:
| 串口 | ESP32引脚功能 | 默认GPIO |
| -- | --------- | ------ |
| TX | 串口发送      | GPIO17 |---------WLED  RX  GPIO3
| RX | 串口接收      | GPIO16 |---------WLED  TX  GPIO1
注意：两者GND需共线
