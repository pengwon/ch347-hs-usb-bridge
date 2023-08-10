# CH347 USB High Speed Bridge

[中文](README.md)

## Introduction

CH347 USB High Speed Bridge is a powerful debugging tool based on the CH347 chip developed by Qinheng Electronics. It supports high-speed USB and provides functionalities such as USB to UART, USB to SPI, USB to I2C, USB JTAG, and USB to GPIO.

![TOP](img/SMT2306162343_T.png)

![BOTTOM](img/SMT2306162343_B.png)

[![](https://mermaid.ink/img/pako:eNqdVMFu2zAM_RVCpwxw4CQNsM63NEELdzVSRA4wDLkwEe1oiCVPogcURfftk521dQZfugthk0_m4-OznsXBKhKJqLRRFdY7A-Cs5dHheDX_DFt5A2zhnrGM09kylo9pvEXH8d1juv4E0MIBRreE3DjybxmAJNEHa0YFQoHjk_bcq43m15NsX3s46vI49jWR6jppw-QKPFAfe58v7oYrgcxwITAdLmwXm3y40s4zUDl3TwdOXMxXn5qy_7U8kxHky68hrNI2rAGNgnwjc_C6NHjqSzW6Rc9QhT10qL3m8R5N2WX6sKsgmuZYAjs0viAHDrnHtdXjw1TlUk4iCHHaxsA4S-WZbbaW6RDbVbYA39S1dZc77fj681F5Ez-01nklGniDp58Nmb647Z7-g_BD10OuFkPs5u9NO2P5f43BOli9hBodVhR6A6ofjeeKzPs4Z6N8fO3fVhFs2pAFKaohetPZZBKc__tL5_89NupyiQFyDQoZW8l8BNN4Bp5t_ffVKhXTLzKxsYbaGTQ_vZ0VkajIVahV-J-f29xO8JEq2okkPCoqsDnxTuzMS4Biw1Y-mYNI2DUUiaYObWmlsQzCiKQIxEOWlGbrsvMd0V0VkajRfLf2FfPyB78dPT8?type=png)](https://mermaid.live/edit#pako:eNqdVMFu2zAM_RVCpwxw4CQNsM63NEELdzVSRA4wDLkwEe1oiCVPogcURfftk521dQZfugthk0_m4-OznsXBKhKJqLRRFdY7A-Cs5dHheDX_DFt5A2zhnrGM09kylo9pvEXH8d1juv4E0MIBRreE3DjybxmAJNEHa0YFQoHjk_bcq43m15NsX3s46vI49jWR6jppw-QKPFAfe58v7oYrgcxwITAdLmwXm3y40s4zUDl3TwdOXMxXn5qy_7U8kxHky68hrNI2rAGNgnwjc_C6NHjqSzW6Rc9QhT10qL3m8R5N2WX6sKsgmuZYAjs0viAHDrnHtdXjw1TlUk4iCHHaxsA4S-WZbbaW6RDbVbYA39S1dZc77fj681F5Ez-01nklGniDp58Nmb647Z7-g_BD10OuFkPs5u9NO2P5f43BOli9hBodVhR6A6ofjeeKzPs4Z6N8fO3fVhFs2pAFKaohetPZZBKc__tL5_89NupyiQFyDQoZW8l8BNN4Bp5t_ffVKhXTLzKxsYbaGTQ_vZ0VkajIVahV-J-f29xO8JEq2okkPCoqsDnxTuzMS4Biw1Y-mYNI2DUUiaYObWmlsQzCiKQIxEOWlGbrsvMd0V0VkajRfLf2FfPyB78dPT8)

## Features

### Overview

- Type-C interface, USB 2.0, supports high-speed mode up to 480Mbps.
- Button for mode switching with hot-plugging support, eliminating the need to unplug the USB connector.
- Built-in EEPROM for configuring working modes, chip VID/PID, maximum current, manufacturer, and product information strings.
- Onboard high-efficiency DC-DC converter providing 5V and 3.3V power outputs with a maximum current of 1A and short-circuit protection.
- Compact size, space-saving, and easy to use.

### UART

- Built-in firmware emulating a standard serial port, used for upgrading existing serial peripheral devices or adding additional serial ports via USB.
- Fully compatible with serial port applications on Windows operating system without modifications.
- Hardware full-duplex UART with independent receive and transmit buffers, supporting baud rates from 1200bps to 9Mbps.
- Supports 8 data bits, odd/even/no parity, and 1 or 2 stop bits.
- Each UART has a built-in 12K-byte receive FIFO and a 4K-byte transmit FIFO.
- Supports commonly used MODEM control signals: RTS, DTR, DCD, RI, DSR, CTS.
- Hardware automatic flow control with CTS and RTS signals.
- Supports half-duplex mode and provides a transmission indicator (TNOW) for controlling RS485 transceiver switching.
- Supports RS232, RS485, RS422, and other interfaces with the use of external level converters.

### SPI

- Host/Master mode.
- Provides SCS, SCK/CLK, MISO/SDI/DIN, MOSI/SDO/DOUT signals.
- Supports 2 chip select (CS) signals for operating two SPI interface devices sequentially.
- Supports 8-bit/16-bit data structure, and both MSB and LSB transfer modes.
- Supports SPI modes 0/1/2/3, configurable transfer frequencies up to 60MHz.
- Hardware DMA for both sending and receiving data.
- Combined with computer APIs, flexible control of 4-wire SPI interface devices like FLASH, MCU, and sensors.

### I2C

- Host/Master mode.
- Provides SCL and SDA signals, supports 4 different transmission speeds.
- Combined with computer APIs, flexible control of 2-wire I2C interface devices like A/D, D/A, EEPROM, and sensors.

### JTAG

- Host/Master mode.
- Provides TMS, TCK, TDI, TDO, and TRST (optional) signals.
- Supports high-speed USB data transfer.
- Combined with computer APIs, flexible control of CPU, DSP, FPGA, CPLD, MCU, and other devices.

### GPIO

- Supports up to 8 GPIO pins for input/output operations.

## Operating Modes

K1 and K2 control the output level. '0' represents pressed, '1' represents released. The table below shows the modes and interface functionalities.

| K1 | K2 | Mode | Interface Functionality |
|----|----|------|------------------------|
| 1  | 1  | 0    | UART0 + UART1          |
| 0  | 1  | 1    | UART1 + SPI + I2C (CDC) |
| 1  | 0  | 2    | UART1 + SPI + I2C (HID) |
| 0  | 0  | 3    | UART1 + JTAG           |

Mode Switching:

On power-up, the default mode is Mode 0. Hold down K1 and press RST to switch to Mode 1. Hold down K2 and press RST to switch to Mode 2. Hold down both K1 and K2, then press RST to switch to Mode 3.

## PINOUT

## Directory Structure

- [Schematics](./sch/)
- [PCB](./pcb/)
- [Enclosure](./3d/)

## Debugging Records

1. [Example of CH347 Dynamic Library Encapsulation](https://mp.weixin.qq.com/s?__biz=MzA3NzMyNTIyOA==&mid=2651481701&idx=1&sn=2ddf1ce70703550bbcaeb7bed4aa0211&chksm=84ad70a6b3daf9b036b859b8b4c621c7a8db6a32ca1e04bd9369b7dc125e17ed16f3ebddc608#rd)

## Related Projects

- [WIP] [CH347 Python Library](https://github.com/pengwon/ch347-py)
