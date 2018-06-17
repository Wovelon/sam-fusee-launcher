# sam-fusee-launcher - Fork for Adafruit Feather M0 & Feather MicroSD support for payload-storage & Feather OLED support for display
Fusee Launcher for the SparkFun SAMD21 breakout boards. Based on [Fusee Launcher](https://github.com/reswitched/fusee-launcher).

Built and tested with PlatformIO but the Arduino IDE probably works also.

[Video of it in action](https://i.imgur.com/sbv75wV.mp4)

## Supported boards:
- [SparkFun SAMD21 Dev Breakout](https://www.sparkfun.com/products/13672)
- [SparkFun SAMD21 Mini Breakout](https://www.sparkfun.com/products/13664)
- Adafruit Feather M0 boards - see below

Note that the Switch does NOT provide power in RCM, so you will need to power the boards from a battery or something else!

## Fork notes:
- In PlatformIO on the Home screen go to libraries and install "SD by Arduino" (tested with v1.2.2), "Adafruit Feather OLED by Adafruit" (tested with v1), "Adafruit GFX Library by Adafruit" (tested with v1.2.3) and "Adafruit SSD1306 by Adafruit" (tested with v1.1.2)
- To flash Adafruit Feather M0, press Reset twice -> red LED blinks...
- MicroSD card has to be formatted with FAT16/FAT32! The main payload binary is "PAYLOAD.BIN", other payloads have to be named "*.BIN" and have to be saved in the main directory.
- Remember to set the correct chipSelect pin for your board in main.cpp! 
- Sparkfun boards use "Serial", Adafruit Feather boards use "Serial1" for terminal (3.3v, e.g. via FTDI)
- My code is ugly - could use some refactoring... :-)
- Photo of Adafruit M0 Adalogger (with MicroSD card) + Adafruit FeatherWing OLED + LiPo Battery 150mA + AmazonBasics Micro-USB to USB-C cable:
![Image](https://github.com/Wovelon/sam-fusee-launcher/blob/master/myasfl.jpg)

### Used the following Adafruit products:
- A feather board + MicroSD card reader: [Adafruit Feather M0 Adalogger](https://www.adafruit.com/product/2796) OR [Adafruit Feather M0 Basic Proto](https://www.adafruit.com/product/2772) + [Adalogger FeatherWing - RTC + SD Add-on](https://www.adafruit.com/product/2922)
- A LiPo battery: [Lithium Ion Polymer Battery - 3.7v 150mAh](https://www.adafruit.com/product/1317) OR [Lithium Ion Polymer Battery - 3.7v 350mAh](https://www.adafruit.com/product/2750)
- Optional - [Adafruit FeatherWing OLED - 128x32 OLED Add-on](https://www.adafruit.com/product/2900) -> for choosing payloads and displaying status -> use "#define USEDISPLAY"
- Optional: [Slide Switch](https://www.adafruit.com/product/805) - [HowTo](https://io.adafruit.com/blog/tip/2016/12/14/feather-power-switch/) -> Haven't tried this one but may be useful :-)
- Optional - for serial console: [Adafruit FTDI Friend + extras - v1.0](https://www.adafruit.com/product/284) -> ATTENTION: Set VCC out to 3.3v!
