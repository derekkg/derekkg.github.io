---
title: Playing sounds using external interrupts on a Raspberry Pi
author: Derek Gutheil
layout: post
permalink: /playing-sounds-using-external-interrupts-on-a-raspberry-pi/
categories:
  - Hardware
  - Raspberry Pi
  - Software
tags:
  - danger zone
  - door
  - interrupt
  - poll
  - polling
  - Raspberry Pi
  - sensor
  - welcome
---
This is a project demonstrating the hardware driven interrupt capability of the Raspberry Pi. The Raspberry Pi can be idle for nearly all of its runtime, and then execute a simple command (In this case, play an audio file) when an external action is completed. This demonstrates how the Raspberry Pi could potentially be used for a much larger home automation or security system, as it would be able to monitor many additional sensors without becoming bogged down by multiple polling requests. In this case the sensor being used is a simple magnetic door switch that switches when the door is opened, triggering the external interrupt on the Raspberry Pi.