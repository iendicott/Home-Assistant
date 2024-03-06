# SunSynk Inverters and Home Assistant ESPHome

This project has been created to allow you to gain back control over your SunSynk Inverter. This applies to 3.68kW / 5.5kW and 8.8kW inverters. (Other models may work)

<br>

**It should be noted, there are different versions of the each inverter. Some have an all in one BMS 485/CAN port like a picture of this 8.8kW SunSynk Inverter**

![8.8KW inverter](<8.8KW inverter.png>)

**and some have seperate CAN and RS485 ports like this picture of a 5.5kW SunSynk Inverter**

![5.5KW inverter](<5.5KW inverter.png>)

<br>
<br>

## Components required

<br>

WEMOS ESP32 Lite V1.0.0 Lolin32 Wifi Bluetooth Board CH340G MicroPython.

![ESP32 Lite](ESPLite.png)

https://kunkune.co.uk/shop/esp32-esp8266/wemos-lolin32-esp32-lite-v1-0-0-wifi-bluetooth-board-ch340g-micropython/?fbclid=IwAR130c3W75-MvHVIQRkaq919oVmQM71DfNW_I4CI16sr6qBjoB76vTmjVCs

<br>

RS485 module to TTL with Isolation Single Chip Microcontroller UART Serial Port.

![RS483 to TTL](<RS485 to TTL.png>)

https://kunkune.co.uk/shop/communication-boards/rs485-module-to-ttl-with-isolation-single-chip-microcontroller-uart-serial-port/?fbclid=IwAR0-Ap4bn00M6TSlwINBr1PfITM7QJWwbq9NOitrLwNkRpegcCKPePa97Lg

A suitable USB power supply and enclosure.

I also created a 3D printed box which can be downloaded from here https://www.thingiverse.com/thing:6456451

![](<ESP 3D box.png>)

<br>

## For the SunSynk Inverters with an all in one BMS 485/CAN port
<br>

![8.8KW inverter](<8.8KW inverter.png>)

You should use these pins and coloured cables

![All In One](<All In One.jpg>)

They should be wired like this

![Wiring](Wiring.png)

You will also be required to splice the cable or purchase an RJ45 splitter* 
The reason behind this is you will not only connect in the ESP32 but you will also need to connect in the existing battery BMS cable.
Luckily the ESP use pins 1 & 2 and the BMS uses pins 4 & 5.

![Pin Outs Combined](<Pin Outs Combined.png>)

<br>

## *Not all splitters are equal. 

In this version you can see it's crossed over, this will NOT work.

![No Good RJ45 Splitter](<No Good RJ45 Splitter.png>)

You will need one like this https://solar-assistant.io/shop/products/deye_rj45_split

![Good Splitter](<Good Splitter.png>)

<br>

## For the SunSynk Inverters with separate CAN & RS485 Ports.
<br>

![5.5KW inverter](<5.5KW inverter.png>)

You can see with a torch behind th cicuit board the pinouts are different

![alt text](<RS485 Pins.png>)

So based on the above you should use these pins and coloured cables

![Seperate](Seperate.jpg)

They should be wired like this

![Alternative Wiring](<Alternative Wiring.png>)

<br>

## Inverter Settings

Under the Advance Tab ensure the following settings are set.
Your inverter will need to be rebooted as it will drop into error mode. Once done your inverter will be back to normal.

![Inverter Settings](<Inverter Settings.jpg>)

<br>

## Flashing the ESP with the Code

Load up the ESPHome Add-ons in Home Assistant.

![Home Assistant ESPHome](ESPHome-HA.png)

Click on the **ESPHome** in the Home Assistant Side Bar
Now click on **+ New Device**
Click **Open ESPHome Web**
Now plug your ESP device into your PC with a Data Micro USB cable then click **Connect**

Your device should appear as a COM device, if not check this https://bromleysat.com/installing-drivers-for-the-esp32 for help
You will then be prompted to install the ESP device. Following this through.

Once install you will then need to Edit the ESP device in ESP home and then paste in the code https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20Local%20Control/ESP%20Inverter.yaml

You will need to replace add **!secret** into your Home Assistant config for the code to work.

<br>
To sync the inverter to the Home Assistant time the code has already been added to the Inverter.yaml file you used earlier. This will sync the inverter time every 3600 seconds. 
You can provision a button to "Sync Now". To complete this in **Home Assistant \ Settings \ Device & Services \ Helpers**

Click on **Create Helper**

Scroll down to **Toggle** click on this and then name it Sync Inverter Time

This created a switch beween the Inverter \ ESP32 board and Home Assistant and sends the Home Assistant time to ModBus registers 22-24.

Once you press this you will see in the ESP Logs something along the lines of, this way you know the sync is working


```
[17:33:30][D][homeassistant.binary_sensor:026]: 'input_boolean.sync_inverter_time': Got state ON
[17:33:30][D][binary_sensor:036]: 'Sync Time': Sending state ON
[17:33:30][I][Time Sync:160]: Seconds: 30, Minutes: 33, Hour: 17, Day: 6, Month: 3, Year: 2024
```

<br>

## Connection

Now plug the device via the RJ45 into the inverter and you should see data being displayed. 
You will also have alot of new sensors in Home Assistant with the Prefix **sunsynk logger**

<br>

## Home Assistant Sensors.

![alt text](1.png)
<br>
![alt text](2.png)
<br>
![alt text](3.png)

Once you have built the product you'll need to install ESP Home on your Home Assistant console and then upload this to your ESP device 
https://github.com/iendicott/Home-Assistant/blob/main/SunSynk%20Local%20Control/ESP%20Inverter.yaml

<br>

## Disclaimer.

I do not accept any responsibility for any damage caused to your equipment. Installation is at your own risk.

Big thanks to **https://github.com/tmh88** for the original code
