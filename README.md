# ESP MQTT JSON Digital LEDs with web server and WiFiManager

This project shows a super easy way to get started using Digital LED strips with [Home Assistant](https://home-assistant.io/), a sick, open-source Home Automation platform that can do just about anything. 

The code covered in this repository utilizes [Home Assistant's MQTT JSON Light Component](https://home-assistant.io/components/light.mqtt_json/) and an ESP8266 microcontroller. 

#### Supported Features Include
- RGB Color Selection
- Brightness 
- Flash
- Fade
- Transitions
- Effects with Animation Speed
- Over-the-Air (OTA) Upload from the ArduinoIDE!
- WiFi Manager for first connection settings
- Web simple web server 

Some of the effects incorporate the currrently selected color (sinelon, confetti, juggle, etc) while other effects use pre-defined colors. You can also select custom transition speeds between colors. The transition variable in Home Assistant (HA) also functions to control the animation speed of the currently running animation. The input_slider and automation in the HA configuration example allow you to easily set a transition speed from HA's user interface without needing to use the Services tool. 

The default speed for the effects is hard coded and is set when the light is first turned on. When changing between effects, the previously used transition speed will take over. If the effects don't look great, play around with the slider to adjust the transition speed (AKA the effect's animation speed). 

#### OTA Uploading
This code also supports remote uploading to the ESP8266 using Arduino's OTA library. To utilize this, you'll need to first upload the sketch using the traditional USB method. However, if you need to update your code after that, your WIFI-connected ESP chip should show up as an option under Tools -> Port -> Porch at your.ip.address.xxx. More information on OTA uploading can be found [here](http://esp8266.github.io/Arduino/versions/2.0.0/doc/ota_updates/ota_updates.html). Note: You cannot access the serial monitor over WIFI at this point.  


#### Demo Video
[![Demo Video](http://i.imgur.com/cpW2JAX.png)](https://www.youtube.com/watch?v=DQZ4x6Z3678 "Demo - RGB Digital LED Strip controlled using ESP, MQTT, and Home Assistant")

#### Tutorial Video
[![Tutorial Video](http://i.imgur.com/9UMl8Xo.jpg)](https://www.youtube.com/watch?v=9KI36GTgwuQ "The BEST Digital LED Strip Light Tutorial - DIY, WIFI-Controllable via ESP, MQTT, and Home Assistant")

#### Parts List
- [Digital RGB WS2812 Leds 5 meter roll]
- [Sonoff Basic]
- [220 AC/DC 5v Power Supply 20A 100W]
- [Just a few wires 6 meters 2 x 1.5mm]



#### Wiring Diagram
![alt text](https://github.com/bruhautomation/ESP-MQTT-Digital-LEDs/blob/master/ESP%20MQTT%20Digital%20LEDs%20Wiring%20Diagram.png?raw=true "Wiring Diagram")


#### SAMPLE MQTT PAYLOAD:

```
  SAMPLE PAYLOAD:
  {
    "brightness": 120,
    "color": {
      "r": 255,
      "g": 100,
      "b": 100
    },
    "flash": 2,
    "transition": 5,
    "state": "ON"
  }
```
