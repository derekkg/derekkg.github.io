---
title: 'raspberry pi &#8211; based e36 in car infotainment'
author: Derek Gutheil
layout: article
permalink: raspberry-pi-based-e36-in-car-infotainment/
tags:
  - Hardware
  - Raspberry Pi
  - Software
toc: true
---
Coming soon &#8211; project currently in progress

*****

##Background

This project was an attempt to create an interface to an e36 BMW's IBUS with a raspberry pi. The IBUS is a communications network used to allow many of BMW's controllers to communicate with each other. In the e36 generation of 3 series, this network was only used to allow the radio head unit to interface with the trunk mounted CD changer. The goal of this project was to emulate the CD changer's IBUS interface to make the head unit think that a CD changer was present, while adding new features such as bluetooth that were not available at the time the car was manufactured.

##Hardware

The project consisted of the following:

+ [Raspberry pi][1]

+ [USB IBUS adapter][2]

+ [RN-52 bluetooth adapter][3]

+ [Power supply][5]

##Software

The software for this project was based heavily on [the pyBus interface by ezeakeal][6] but with some modifications of my own to make it suit the needs of my project and my car better. Source for this project [can be found here.][7] 

##Goals

There were a few main goals for this project:

1. Connect a phone via bluetooth to the car and play music over the stock head unit.
2. Be able to control the music from the head unit.
3. Display song information (track title, artist, play duration, etc.) on the head unit's LCD screen.

##Project
The Raspberry Pi is the central controller for this project. It is connected to the IBUS via the usb adapter, and controls the RN-52 bluetooth adapter via GPIO and Serial communications. 


Pictures...


mention garage door opener

##Mistakes and Future Improvements
There are many things I want to improve on this in the future. The hardware I choose for this began to make less sense over various revisions of the design. Originally I had intended to have it connected to the internet to allow for devices to remotely connect to it and lock/unlock the car, open windows, flash the headlights, etc. Unfortunately after some research I discovered that the IBUS implementation on the E36 3 series does not gateway messages from other busses, so only radio commands are valid. This severely limited the scope of the what was possible with this device. I had also originally intended to use a small bluetooth dongle on the Raspberry Pi to enable streaming bluetooth through the Pi. This would have kept the amount of hardware components low, and allowed for everything to be USB based. Unfortunately the built-in DAC on the Raspberry Pi is subpar, and bluetooth streaming was less than ideal over the Pi with frequent cut-outs or glitches. This led to the use of the RN-52 as a complete bluetooth solution. The ability to gather track meta-data and send command to it over UART made it a breeze to integrate with the Pi and kept all of the features I was looking for.

The power supply ended up being more problematic than I had anticipated with alot of noise being transmitted over the power lines. I had hoped that the USB charger would filter that but for the future it looks like I will have to design a filter or isolattion circuit that can remove the noise from the power lines.

It has become obvious now that the Raspberry pi is extreme overkill for this project, and the requiremnets of this can be met by something much less powerful. I am hoping to improve this with a second version that is based on an Arduino or PIC microcontroller, and have it all made on a PCB. This would allow for the power supply, Bluetooth module, and IBUS circuits to be on the same board, drastically reducing the size of this. 


[1]: http://www.raspberrypi.org/products/
[2]: http://www.reslers.de/IBUS/
[3]: www.microchip.com/rn52
[4]: https://www.freedompop.com/devices/freedom-stick-bolt
[5]: http://www.aukey.com/product/24w-dual-port-usb-car-charger-aipower-black
[6]: https://github.com/ezeakeal/pyBus
[7]: https://bitbucket.org/dgutheil/python-ibus-interface