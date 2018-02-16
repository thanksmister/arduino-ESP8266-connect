# Arduino ESP8266 Connect

This Arduino project creates a shared access point for an ESP8266 WiFi module which allows the accompanying [Android application](https://github.com/thanksmister/android-esp8266-connect) to connect and send commands.

# Hardware Requirements
- [Adafruit Feather HUZZAH with ESP8266 WiFi](https://www.adafruit.com/product/2821)
- LED light
- 1k Ohm Resister

# Software Requirements

- [ESP8266 WiFi Arduino Library](https://github.com/esp8266/Arduino/tree/master/doc/esp8266wifi)
- Arduino IDE

# Setup

Download the open the Arduino file in the Arduino IDE.  Be sure you have the ESP8266 library installed.  Compile and deploy to your Feather using the USB cable.  The default access point name is Esp8266TestNet (it's hidden) and the password is Esp8266Test.  These can be changed in the Arduino file.   

You can connect to the access point with your computer or mobile device and then send commands using just a browser. Type http://192.168.4.1/led/0 to turn off the LED light and http://192.168.4.1/led/1 to turn the LED light on.   You can also use the companion Android application to communicate with the ESP8266 module from you Android device. 

# Fritzing Diagram

![Huzzah Diagram](https://github.com/thanksmister/arduino-ESP8266-connect/blob/master/Huzzah_bb.png)
