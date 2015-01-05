---
title: Adruino Android bluetooth RGB LED Controller
author: Derek Gutheil
layout: post
permalink: /adruino-android-bluetooth-rgb-led-controller/
categories:
  - Android
  - Arduino
  - Hardware
  - Software
tags:
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
  - strip
  - touchpad
  - wireless
---
This system allows the user full control over the color of Red Green Blue LED&#8217;s via an intuitive and easy to use android app.

This is one part of a complete in-car infotainment system, see the full infotainment system description [here][1].

Parts list:  
Arduino Uno  
Texas instruments tlc5940  
Bluetooth Serial port adapter  
HP Touchpad running Android 4.0

The Touchpad is sending commands to the Arduino using the Amarino Arduino library and android application over Bluetooth (<http://www.amarino-toolkit.net/>) The Arduino sends these commands to the tlc5940 which controls the RGB led. The Arduino project and Android application are based on the MultiColorLamp example here (<http://www.amarino-toolkit.net/index.php/download.html>) but modified to allow the arduino to communicate with the tlc5940 instead of the RGB led directly using the tlc5940 library (<http://www.arduino.cc/playground/Learning/TLC5940>). The reasoning for this is because in its final installation (car) the arduino controls 8 RGB led&#8217;s not 1. The android application is also being modified to let the user pick a specific color instead of using sliders, and to allow for different timings and patterns.

&nbsp;

A full how-to will be posted in the future

 [1]: http://derekgutheil.com/android-car-infotainment-system/