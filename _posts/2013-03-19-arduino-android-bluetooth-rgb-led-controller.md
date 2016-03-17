---
title: Arduino Android bluetooth RGB LED Controller
author: Derek Gutheil
layout: article
permalink: /adruino-android-bluetooth-rgb-led-controller/
tags:
  - Android
  - Arduino
  - Hardware
  - Software
  - android
  - arduino
  - blue
  - bluetooth
  - color
  - green
  - hp
  - led
  - lights
  - red
  - touchpad
  - wireless
---
This system allows the user full control over the color of Red Green Blue LED's via an intuitive and easy to use android app.

This is one part of a complete in-car infotainment system, see the full infotainment system description [here][1].

Parts list:

+ Arduino Uno  

+ Texas instruments tlc5940  

+ Bluetooth Serial port adapter  

+ HP Touchpad running Android 4.0

The Touchpad is sending commands to the Arduino using the Amarino Arduino library and android application over Bluetooth [2]. The Arduino sends these commands to the tlc5940 which controls the RGB led. The Arduino project and Android application are based on the MultiColorLamp example [here][3] but modified to allow the arduino to communicate with the tlc5940 instead of the RGB led directly using the [tlc5940 library][4]. The reasoning for this is because in its final installation (car) the arduino controls 8 RGB led's not 1. The android application is also being modified to let the user pick a specific color instead of using sliders, and to allow for different timings and patterns.

A full how-to will be posted in the future


<iframe width="560" height="315" src="https://www.youtube.com/embed/Z50HQEto14k" frameborder="0" allowfullscreen></iframe>


 [1]: http://derekgutheil.com/android-car-infotainment-system/
 [2]: http://www.amarino-toolkit.net/
 [3]: http://www.amarino-toolkit.net/index.php/download.html
 [4]: http://www.arduino.cc/playground/Learning/TLC5940