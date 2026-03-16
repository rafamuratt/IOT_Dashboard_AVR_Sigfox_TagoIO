IOT communication using Sigfox and TagoIO dashboard  

🚀 System Overview  
This firmware works on AVR/ Arduino, allowing data messages sending over the Sigfox network to a web dashboard from TagoIO. You can access the dashboard here:    
https://610efe6f94a33700127f37f9.tago.run/dashboards/info/6290e3d3d2408f0013fc16f8?anonymousToken=00000000-610e-fe6f-94a3-3700127f37f9

🛠 Hardware  
* Arduino Nano/ Uno (ATMEGA328P) @16MHz;
* Edukit Redfox (Sigfox SoC HT32SX radio frequency transmitter/ receiver). Note: *any UART SoC should work however the controll messages has to be adapted to it.* 
* PIR sensor - detect movement around;
* Acceleration sensor MPU6050 - detect 3D vibration (x,y and z axes);
* I2C Current/ Voltage sensor INA219 - remote check of instant voltage/ current required from power supply/ batteries
* Two batteries Samsung INR18650-35E (3.7V 3.5Ah each).
* Detailed code explanation in the file: Edukit_IOT_WdT.ino

<<<<< **Note: With the current setup and code to save power, the batteries can last up to 4 days** >>>>>

📂 Project Structure  
/Edukit_IOT_WdT: Contains the *.ino file. A dashboard screenshot is also available.

⚙️ Operational Flow  
The AVR is always in deep sleep mode. It is activated when the sensors are triggered, automatic messages are sent to TagoIO dashboard using the Sigfox network and return to deep sleep.    
IDLE_TIME guarantees a maximum of one message every 5 minutes, MSG_LIMIT guarantees max 30 msg for testing purposes.   
In case of recursive error the service stops to save credits. In this case, the user has to perform a hard reset (Ack under push button) to proceed.   
The messages IDs depends of sensor activated and differentiates between:
* ID1: Regular message, ID2: Regular message (new try in case of error); both IDs when only PIR sensor is activated.
* ID4: Special message, ID5: Special message (new try in case of error); both IDs when PIR + vibration MPU6050 sensors are activated.
* ID7 and ID8: Alarm messages that stops the service. ID7: when MSG_LIMIT is reached; ID8: after consecutive fails or unknown errors (until manual reset of device) to protect your Sigfox credits in case of issues.  

Additional info on Murat-Tech Channel BR: https://www.youtube.com/watch?v=eSdl9WC-ug8

📜 License  
This project is licensed under the Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

☕ If this project is helpfull for your application, please consider to support:  
https://www.paypal.com/donate/?hosted_button_id=8S8BJ9TT368VN

Built by rafamuratt: https://murat-tech.eu/  
Murat-Tech Channel: https://www.youtube.com/@Murat-TechChannel-EN










