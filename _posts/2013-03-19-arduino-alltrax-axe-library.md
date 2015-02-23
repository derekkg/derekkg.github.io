---
title: Arduino Alltrax AXE Library
author: Derek Gutheil
layout: article
permalink: arduino-alltrax-axe-library/
tags:
  - Alltrax
  - Android
  - EV Team
  - Software
image:
  teaser: bio-photo.jpg
  feature: 400x250.gif
  credit: Derek Gutheil #name of the person or site you want to credit
  creditlink: www.derekgutheil.com #url to their site or licensing
toc: true
---

An Arduino Library for interfacing an Arduino with an Alltrax AXE/DCX motor controller. Any information that the motor controller is monitoring can be viewed on the Arduino, and writeable parameters on the Alltrax can be written by the Arduino as well. It may work for other Alltrax series motor controllers, however only the AXE series has been tested. 

Based on work by [Jennifer Holt](http://jennwork.homelinux.net/drupal6/node/26) and [Alltrax](http://www.mail-archive.com/listserv@electricmotorcycles.net/msg01779.html)


<p style="text-align: center;"><strong>Please NOTE: an RS232 Adapter is necessary!</strong></p>


## Installation and Examples

Unzip the Alltrax.zip folder into the arduino/libraries/ folder. Then look at the ReadUse example (File -> Examples -> Alltrax -> ReadUse).

## The Circuit

<p style="text-align: center;"><strong>
an RS232 Adapter is necessary</strong><br /> * Power and ground &#8211;> RS232 shield/adapter<br /> * Arduino Rx &#8211;> adapter Rx<br /> * Arduino Tx &#8211;> adapter Tx
</p>

If you do not have a crossover or null modem cable, you may need to switch which pin goes to Rx and Tx. A crossover or null modem cable is simply one where the Tx and Rx lines are switch internally. See <http://upload.wikimedia.org/wikipedia/commons/5/57/D25_Null_Modem_Wiring.png> for details.

## Versions:

There are 2 versions of this Library: One for Hardware Serial and one for Software Serial.  
For more information on Software Serial see here: <http://arduino.cc/en/Reference/SoftwareSerial>

## How to use:

Using each Library is a little different:

####Hardware

The only tricky part about this is that you need to pass a serial object to the begin() function of the library by reference before doing anything else. The reason for doing this is that it allows different Arduinos that implement Serial differently to all use the same library. In practice it would look something like this:

    #include 
    Alltrax controller;
    …
    …
    void setup() {
    controller.begin(&Serial1);
    …
    …

Here is a table showing which hardware serial should be used:
        
| Board                                                                              | Hardware Serial                   |
|------------------------------------------------------------------------------------|-----------------------------------|
| Uno, Ethernet, Bluetooth, Duemilanove,Nano, Pro, Mini, etc. ATmega168 or ATmega328 | Serial                            |
| Due, Mega2560                                                                      | Serial, Serial1, Serial2, Serial3 |
| Leonardo, Micro                                                                    | Serial1                           |      

See the provided examples if there is any confusion.
                                          
####Software

The only real difference between the Software and Hardware implementations is the instantiation. In the software version, you need to create a SoftwareSerial object with your Rx and Tx pins and then pass that by reference to the AlltraxSoftwareSerial **constructor**. Note there is no begin() method for the SoftwareSerial version.

It could look something like this:

    #include <SoftwareSerial.h>
    #include <AlltraxSoftwareSerial.h>
    …
    …
    SoftwareSerial mySerial(10,11); // Rx, Tx
    AlltraxSoftwareSerial controller(&mySerial);
    …
    …

####Methods

There will be a page with method descriptions up shortly, in the mean time, the header file should suffice.

####Project Page

There will be a google code / github page up shortly

####Download

**Hardware:** [Alltrax.zip](http://derekgutheil.com/wp-content/uploads/2013/05/Alltrax.zip)

**Software:** [AlltraxSoftwareSerial.zip](http://derekgutheil.com/wp-content/uploads/2013/05/AlltraxSoftwareSerial.zip)