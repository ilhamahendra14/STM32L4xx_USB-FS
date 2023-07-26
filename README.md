# STM32L4xx_USB-FS
**Repository for USB-FS (Device) - CDC (Communication Device Class (Virtual Port Com))**

## Hardware 
For testing you can directly connect D+ to USB_DP (PA12), and D- to USB_DM (PA11). 
![alt text](https://github.com/ilhamahendra14/STM32L4xx_USB-FS/blob/24d2a5c4390c9015f123c1717fa9d9488887519d/Images/USB_Type-C_Schematic.png?raw=true)

## Firmware
+ To transmit data, please call the 'CDC_Transmit_FS' function.
  ```C
  CDC_Transmit_FS(Buf, Len);
  ```
+ To receive data, please check the 'CDC_Receive_FS' function in the 'USB_DEVICE/App/usbd_cdc_if.c' directory.
  ```C
  static int8_t CDC_Receive_FS(uint8_t* Buf, uint32_t *Len)
  {
    /* USER CODE BEGIN 6 */
    USBD_CDC_SetRxBuffer(&hUsbDeviceFS, &Buf[0]);
    USBD_CDC_ReceivePacket(&hUsbDeviceFS);
    printf(Buf);
    return (USBD_OK);
    /* USER CODE END 6 */
  }
  ```
  ![alt text](https://github.com/ilhamahendra14/STM32L4xx_USB-FS/blob/24d2a5c4390c9015f123c1717fa9d9488887519d/Images/Device_Receive.png?raw=true)

## Host/PC
+ The STM32 board will be detected in 'Device Manager' as 'USB Serial Device(COMxx)'.

  ![alt text](https://github.com/ilhamahendra14/STM32L4xx_USB-FS/blob/24d2a5c4390c9015f123c1717fa9d9488887519d/Images/Device_Manager_COMPorts.png?raw=true)
+ To receive/transmit data I open serial with 115200 baudrate 8N1.

  ![alt text](https://github.com/ilhamahendra14/STM32L4xx_USB-FS/blob/24d2a5c4390c9015f123c1717fa9d9488887519d/Images/Host_Receive_2.png?raw=true)
