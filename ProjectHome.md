http://wiki.yanis-android-wireless-camera-controller.googlecode.com/git/wimg/IMG_7576.JPG

http://wiki.yanis-android-wireless-camera-controller.googlecode.com/git/wimg/IMG_7623%20(Small).JPG

http://wiki.yanis-android-wireless-camera-controller.googlecode.com/git/wimg/IMG_7624%20(Small).JPG

http://wiki.yanis-android-wireless-camera-controller.googlecode.com/git/wimg/IMG_7647%20(Small).JPG

http://wiki.yanis-android-wireless-camera-controller.googlecode.com/git/wimg/IMG_7651%20(Small).JPG







---


**Current features:**

Manual control over:

  * Aperture
  * Shutter Speed
  * ISO
  * White Balance
  * Focus Position
  * Live View STATUS
  * Capture



**Upcoming Features**

  * Video mode
  * **Rack Focusing**
  * Intervalometer/timer
  * HDR Bracketing
  * _Bracketed_ intervalometer
  * Arduino Side Battery life optimizations (about 80% improvement expected)
  * **Multiple** camera control


---



**Architecture Overview**



This project consists of 2 components:

  1. The **Arduino** side
  1. The **Android** side


The Arduino side uses an Arduino board together with a USB Host Shield(based on MAX3421E) and a RFCOMM compatible Bluetooth module. This system will connect to the EOS Camera via its USB port and will control the camera via Canon's implementation of the PTP protocol.

The Arduino will run a code (heavily based on the excellent work done by Oleg Mazurov from www.circuitathome.com) that will handle the PTP protocol implementation by using the USB host. Secondly, it will 'translate' serial commands received from the Bluetooth module into actual PTP commands. These two features work together to effectively allow the (complex) PTP protocol to be _simplified to mere serial commands._

The set of serial commands that the Arduino will accept to perform the corresponding PTP command translation will be referred to as the '**Manis Command Set**' (or **MCS**) throughout this project. Shameless self-promotion? Check.


The Second part of the project consists of an Android application which will connect the Android device via Bluetooth to the previously described Arduino system. It will provide a user interface and send out the relevant '_MCS-compliant_' commands depending on what the user wants to do. It currently is available for free on the Android market.


The Arduino system will then receive those MCS commands and translate them into corresponding PTP-Commands.


---


**Hardware Instructions**

Hardware build instructions available here: http://theiopage.blogspot.com

More in-depth instructions to follow.


---


**Android Instructions**

1. Get the App here:
https://market.android.com/details?id=appinventor.ai_manis404.YaNis_Controller

2. Pair the Arduino side bluetooth module to your Android device.

3. Make sure it is **paired** correctly.

4. Open up the application, click "BT Device" then select the device corresponding to the Arduino Bluetooth module.

5. Connect.


---


**Source Code**

Updated source code will be progressively added.

Visit the Downloads section for the source code.


---

**Video Demo**

<a href='http://www.youtube.com/watch?feature=player_embedded&v=3_SF-b7aH58' target='_blank'><img src='http://img.youtube.com/vi/3_SF-b7aH58/0.jpg' width='425' height=344 /></a>





---

**Additional Notes**



The current version as of 29/08/11 "officially" supports the 1000D, 450D, 400D cameras. But theoretically, it should work with most other Canon DSLRs too.



I can add "official" support for additional models depending on public interest.



Also, please feel free to report issues in comments or the Issues section.


Project status: BETA (Read: WE NEED TESTERS!)

