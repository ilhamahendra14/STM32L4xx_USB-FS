# STM32L4xx_USB-FS
**Repository for USB-FS (Device) - CDC (Communication Device Class (Virtual Port Com))**

## Hardware 
For testing you can directly connect D+ to USB_DP (PA12), and D- to USB_DM (PA11). You can check [the schematic](/USB_Type-C_Schematic.png).

## Firmware
+ To transmit data, please call the 'CDC_Transmit_FS' function.
+ To receive data, please check the 'CDC_Receive_FS' function in the 'USB_DEVICE/App/usbd_cdc_if.c' directory.

## Host/PC
+ The STM32 board will be detected in 'Device Manager' as 'USB Serial Device(COMxx)'.
+ To receive/transmit data I open serial with 115200 baudrate 8N1.
