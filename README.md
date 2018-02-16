# Arduino ESP8266 Connect

This Arduino project creates a shared access point using an ESP8266 WiFi module which allows an accompanying [Android application](https://github.com/thanksmister/android-esp8266-connect) to connect and send commands to control a LED light. 

# Hardware Requirements
- [Adafruit Feather HUZZAH with ESP8266 WiFi](https://www.adafruit.com/product/2821)
- LED light
- 1k Resistor
- 

# Software Requirements

- [ESP8266 WiFi Arduino Library](https://github.com/esp8266/Arduino/tree/master/doc/esp8266wifi)
- Arduino IDE
- [Android application](https://github.com/thanksmister/android-esp8266-connect) 

# Setup

Download and open the Arduino file in the Arduino IDE.  Be sure you have the ESP8266 library installed.  Use the Fritzing diagram to setup the LED light:

![Huzzah Diagram](https://github.com/thanksmister/arduino-ESP8266-connect/blob/master/Huzzah_bb.png)

Compile and deploy the project to your ESP8266.  The default access point name is "Esp8266TestNet" (it's a hidden network) and the password is "Esp8266Test".   You may have to create the network manually.   The access point will be created automatically on start of the ESP8266 device.

These can be changed in the Arduino file at the top. 

```
// WiFi Definitions
const char* ssid = "Esp8266TestNet";
const char* password = "Esp8266Test"; // has to be longer than 7 chars
```

You can connect to the access point from your computer or mobile device and then send commands using a browser.  Once you have successfully connected to the access point Esp8266TestNet, enter "http://192.168.4.1/led/0" to turn off the LED light and "http://192.168.4.1/led/1" to turn the LED light on.  Notice the server address is 192.168.4.1. 


You can connect to the access point from your computer or mobile device and then send commands using a browser.  Once you have successfully connected to the access point Esp8266TestNet, enter "http://192.168.4.1/led/0" to turn off the LED light and "http://192.168.4.1/led/1" to turn the LED light on. Notice the server address is 192.168.4.1. 

# Android Application Setup 

You can use the companion [Android application](https://github.com/thanksmister/android-esp8266-connect) to communicate with the ESP8266 module from your Android device.   Download the APK file from the Android Github repository release section and side load onto your mobile device.   If you wish to, you can also checkout the Github repository and build the APK file using Android Studio. 


