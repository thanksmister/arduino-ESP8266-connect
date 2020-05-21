# Arduino ESP8266 Connect

This Arduino project creates a WiFi access point using an ESP8266 WiFi module which allows an accompanying [Android application](https://github.com/thanksmister/android-esp8266-connect) to connect and send commands to control a LED light.

[Hackster Project](https://www.hackster.io/thanksmister/android-to-esp8266-comunication-a84f50)

You can also join the [ThanksMister Community](https://community.thanksmister.com/) to ask questions or share any helpful information about this project. 

# Hardware Requirements
- [Adafruit Feather HUZZAH with ESP8266 WiFi](https://www.adafruit.com/product/2821)
- LED light
- 1k Resistor

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

You can connect to the access point from your computer or mobile device and then send commands using a browser.  Once you have successfully connected to the access point Esp8266TestNet, enter "http://192.168.4.1/led/off" to turn off the LED light and "http://192.168.4.1/led/on" to turn the LED light on.  Notice the server address is 192.168.4.1. 

The access point will return a HTTP 200 response along with a JSON result with success and off/on value received: 

```
{"data":{"message":"success", "value":"off"}} 
```

You can connect to the access point from your computer or mobile device and then send commands using a browser.  Once you have successfully connected to the access point Esp8266TestNet, enter "http://192.168.4.1/led/0" to turn off the LED light and "http://192.168.4.1/led/1" to turn the LED light on. Notice the server address is 192.168.4.1. 

# Android Application Setup 

You can use the companion [Android application](https://github.com/thanksmister/android-esp8266-connect) to communicate with the ESP8266 module from your Android device.   Download the APK file from the Android Github repository release section and side load onto your mobile device. If you wish to, you can also checkout the Github repository and build the APK file using Android Studio. 

Open the installed application on your device and select the "Connect" button.  This will connect to the access point with the default name and password.  If you wish to change these, you can do so under the settings from the drop down menu.  

Once you connect, you can use the "Send" buttons below the values to toggle on/off the LED light. Use the "Disconnect" button to disconnect from the access point and return reconnect to your previous WiFi connection.  


