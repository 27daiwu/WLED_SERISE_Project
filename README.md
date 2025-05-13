
#  WLED_Serise_Project WITH JSON API
这是一个非常简单的示例代码，展示了如何使用PlatformIO通过串行接口与[WLED](https://github.com/Aircoookie/WLED) JSON API进行交互。借助WLED JSON API，您能够使用所有API命令来控制任何其他具有串行能力的微控制器上闪存了WLED的MCU。在我的示例草图中，通过按下连接到发送MCU的按钮，可以更改WLED-MCU上LED灯条的颜色。

## Setup:
- 发送的微控制器: esp32
- 接收的微控制器: esp32，使用WLED0.15
- WLED版本: "WLED-0.15"- 波特率: 115200

## Note:
SoftwareSerial 仅适用于非常低的波特率，绝对不适合 921600。如果可能，您应该始终使用 HardwareSerial；如果 SoftwareSerial 是不可或缺的，请使用尽可能低的波特率。
本代码用HardwareSerial，波特率115200

## Connections:
| 串口 | ESP32引脚功能 | 默认GPIO |
| -- | --------- | ------ |
| TX | 串口发送      | GPIO17 |---------WLED  RX  GPIO3
| RX | 串口接收      | GPIO16 |---------WLED  TX  GPIO1
注意：两者GND需共线
