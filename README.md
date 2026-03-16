IOT_Dashboard_AVR_Sigfox_TagoIO

IOT communication using Sigfox and TagoIO dashboard

?? System Overview
This firmware works on AVR/ Arduino, allowing data messages sending over the Sigfox network to a web dashboard from TagoIO. The dashboard can be accesed here:
https://610efe6f94a33700127f37f9.tago.run/dashboards/info/6290e3d3d2408f0013fc16f8?anonymousToken=00000000-610e-fe6f-94a3-3700127f37f9

The messages Id's differentiates them between:
* normal message.
* special message.
* message resent (in case of error). 
* alarm message (it stops the local services until manual reset of device) to protect your Sigfox credits in case of issues.

?? Hardware
* Arduino Nano/ Uno (ATMEGA328P) @16MHz;
* Edukit Redfox (Sigfox SoC HT32SX radio frequency transmitter/ receiver). Note: any UART SoC should work however the controll messages has to be adapted to it. 
* PIR sensor - detect movement around;
* Acceleration sensor MPU6050 - detect 3D vibration (x,y and z axes);
* Current sensor INA219 - reads the instant voltage and current required from power supply
* Two batteries Samsung INR18650-35E (3.7V 3.5Ah each).
* Detailed code explanation in the file: Edukit_IOT_WdT.ino

<<<<< Note: With the current setup and code to save power, the batteries can last up to 4 days >>>>>

Additional info on Murat-Tech Channel BR: https://www.youtube.com/watch?v=eSdl9WC-ug8

?? License
This project is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

If this project is helpfull for your application, please consider to support:
https://www.paypal.com/donate/?hosted_button_id=8S8BJ9TT368VN

Built by rafamuratt: https://murat-tech.eu/










