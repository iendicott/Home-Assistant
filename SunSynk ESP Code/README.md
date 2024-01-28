# SunSynk-ESPHome

ESPHome Project to establish communication with SunSynk 8.8kW & 5.5kW Inverter via RS485 Modbus.
The code is based on Modbus registers from SunSynk.


## Components.

WEMOS ESP32 Lite V1.0.0 Lolin32 Wifi Bluetooth Board CH340G MicroPython.

 ![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/ESPLite.png)

https://kunkune.co.uk/shop/esp32-esp8266/wemos-lolin32-esp32-lite-v1-0-0-wifi-bluetooth-board-ch340g-micropython/?fbclid=IwAR130c3W75-MvHVIQRkaq919oVmQM71DfNW_I4CI16sr6qBjoB76vTmjVCs

RS485 module to TTL with Isolation Single Chip Microcontroller UART Serial Port.

 ![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/RS485%20to%20TTL.png)

https://kunkune.co.uk/shop/communication-boards/rs485-module-to-ttl-with-isolation-single-chip-microcontroller-uart-serial-port/?fbclid=IwAR0-Ap4bn00M6TSlwINBr1PfITM7QJWwbq9NOitrLwNkRpegcCKPePa97Lg

USB power supply and suitable enclosure.

## Connections.

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/Wiring.png)

## 5.5kW & 8.5kW with combind BMS 2in1 Port.

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/Connector.png)

The 8kW inverter uses a combined BMS 2in1 Port located below.

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/8kw.png)

## 5.5kW with Separate CAN & RS485 Ports.

Use Pins 1 & 7 as pin2 isn’t connected on the PCB

Pin1 = Orange/White = (A)

Pin7 = Brown/White = (B)


![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/5.5%20inverter.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/RS485%20Pins.png)


## Inverter Settings.

Under the Advance Tab ensure the following settings are set.

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/Inverter%20Settings.png)

## Home Assistant Sensors.

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS1.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS2.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS3.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS4.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS5.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS6.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS7.png)

![image](https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/SS8.png)

Once you have built the product you'll need to install ESP Home on your Home Assistant console and then upload this to your ESP device 
https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20ESP%20Code/ESP%20Inverter.yaml

## Disclaimer.
The project is something I have developed and researched myself. I cannot accept any responsibility for any damage caused to your equipment. Please install at your own risk.

