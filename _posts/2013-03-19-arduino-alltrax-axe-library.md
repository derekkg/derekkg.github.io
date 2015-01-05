---
title: Arduino Alltrax AXE Library
author: Derek Gutheil
layout: post
permalink: /arduino-alltrax-axe-library/
categories:
  - Alltrax
  - Android
  - EV Team
  - Software
---
An Arduino Library for interfacing an Arduino with an Alltrax AXE/DCX motor controller. Any information that the motor controller is monitoring can be viewed on the Arduino, and writeable parameters on the Alltrax can be written by the Arduino as well. It may work for other Alltrax series motor controllers, however only the AXE series has been tested. 

Based on work by Jennifer Holt (<a href="http://jennwork.homelinux.net/drupal6/node/26" rel="nofollow">http://jennwork.homelinux.net/drupal6/node/26</a>)  
and Alltrax (<a href="http://www.mail-archive.com/listserv@electricmotorcycles.net/msg01779.html" rel="nofollow">http://www.mail-archive.com/listserv@electricmotorcycles.net/msg01779.html</a>)

&nbsp;

<p style="text-align: center;">
  <strong>Please NOTE: an RS232 Adapter is necessary!</strong>
</p>

&nbsp;

### Installation and Examples

Unzip the Alltrax.zip folder into the arduino/libraries/ folder.

Then look at the ReadUse example (File -> Examples -> Alltrax -> ReadUse).

&nbsp;

### The Circuit

<p style="text-align: center;">
  <strong>an RS232 Adapter is necessary</strong><br /> * Power and ground &#8211;> RS232 shield/adapter<br /> * Arduino Rx &#8211;> adapter Rx<br /> * Arduino Tx &#8211;> adapter Tx
</p>

<p style="text-align: left;">
  If you do not have a crossover or null modem cable, you may need to switch which pin goes to Rx and Tx. A crossover or null modem cable is simply one where the Tx and Rx lines are switch internally. See <a href="http://upload.wikimedia.org/wikipedia/commons/5/57/D25_Null_Modem_Wiring.png">http://upload.wikimedia.org/wikipedia/commons/5/57/D25_Null_Modem_Wiring.png</a> for details.
</p>

&nbsp;

### Versions:

There are 2 versions of this Library: One for Hardware Serial and one for Software Serial.  
For more information on Software Serial see here: <http://arduino.cc/en/Reference/SoftwareSerial>  
&nbsp;

### How to use:

Using each Library is a little different:

<p style="text-align: center;">
  <strong>&#8212;&#8211; Hardware</strong>: &#8212;&#8211;
</p>

The only tricky part about this is that you need to pass a serial object to the begin() function of the library by reference before doing anything else. The reason for doing this is that it allows different Arduinos that implement Serial differently to all use the same library. In practice it would look something like this:

&nbsp;

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td valign="top" width="300">
      <p>
        #include <Alltrax.h><br /> Alltrax controller;<br /> &#8230;<br /> &#8230;<br /> void setup() {<br /> &nbsp;&nbsp;controller.begin(&Serial1);<br /> &#8230;<br /> &#8230;</td> </tr> </tbody> </table> 
        
        <p>
          Here is a table showing which hardware serial should be used:<br /> &nbsp;
        </p>
        
        <table width="90%" border="1" cellpadding="5">
          <tr>
            <td align="left">
              <strong></p> 
              
              <p>
                Board</strong></td> 
                
                <td>
                  <strong></p> 
                  
                  <p>
                    Hardware Serial</strong></td> </tr> 
                    
                    <tr>
                      <td align="left">
                        <p>
                          Uno, Ethernet, Bluetooth, Duemilanove,<br /> Nano, Pro, Mini, etc. ATmega168 or ATmega328</td> 
                          
                          <td>
                            <p>
                              Serial</td> </tr> 
                              
                              <tr>
                                <td align="left">
                                  <p>
                                    Due, Mega2560</td> 
                                    
                                    <td>
                                      <p>
                                        Serial, Serial1, Serial2, Serial3</td> </tr> 
                                        
                                        <tr>
                                          <td align="left">
                                            <p>
                                              Leonardo, Micro</td> 
                                              
                                              <td>
                                                <p>
                                                  Serial1</td> </tr> </tbody> </table> 
                                                  
                                                  <p>
                                                    See the provided examples if there is any confusion.<br /> &nbsp;
                                                  </p>
                                                  
                                                  <p>
                                                    &nbsp;
                                                  </p>
                                                  
                                                  <p style="text-align: center;">
                                                    <strong>&#8212;&#8211; Software</strong>: &#8212;&#8211;
                                                  </p>
                                                  
                                                  <p style="text-align: left;">
                                                    The only real difference between the Software and Hardware implementations is the instantiation. In the software version, you need to create a SoftwareSerial object with your Rx and Tx pins and then pass that by reference to the AlltraxSoftwareSerial <strong>constructor.</strong> Note there is no begin() method for the SoftwareSerial version.
                                                  </p>
                                                  
                                                  <p>
                                                    It could look something like this:
                                                  </p>
                                                  
                                                  <table border="1" cellspacing="0" cellpadding="0">
                                                    <tr>
                                                      <td valign="top" width="300">
                                                        <p>
                                                          #include <SoftwareSerial.h><br /> #include <AlltraxSoftwareSerial.h><br /> &#8230;<br /> &#8230;<br /> SoftwareSerial mySerial(10,11); // Rx, Tx<br /> AlltraxSoftwareSerial controller(&mySerial);<br /> &#8230;<br /> &#8230;</td> </tr> </tbody> </table> 
                                                          
                                                          <p>
                                                            &nbsp;
                                                          </p>
                                                          
                                                          <h3>
                                                            Methods
                                                          </h3>
                                                          
                                                          <p>
                                                            There will be a page with method descriptions up shortly, in the mean time, the header file should suffice
                                                          </p>
                                                          
                                                          <p>
                                                            &nbsp;
                                                          </p>
                                                          
                                                          <h3>
                                                            Project Page
                                                          </h3>
                                                          
                                                          <p>
                                                            There will be a google code / github page up shortly
                                                          </p>
                                                          
                                                          <p>
                                                            &nbsp;
                                                          </p>
                                                          
                                                          <h3>
                                                            Download
                                                          </h3>
                                                          
                                                          <p>
                                                            <strong>Hardware:</strong> <a title="Alltrax.zip" href="http://derekgutheil.com/wp-content/uploads/2013/05/Alltrax.zip">Alltrax.zip</a>
                                                          </p>
                                                          
                                                          <p>
                                                            <strong>Software:</strong> <a title="AlltraxSoftwareSerial.zip" href="http://derekgutheil.com/wp-content/uploads/2013/05/AlltraxSoftwareSerial.zip">AlltraxSoftwareSerial.zip</a>
                                                          </p>