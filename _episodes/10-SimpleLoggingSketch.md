---
title: "First Sketch: simple_logging.ino"
teaching: 10
exercises: 20
questions:
- "How do I run multiple sensors and log to an SD card?"
objectives:
- "Run BME280 and DS18 sensors with simple_logging.ino."
keypoints:
- "Simple logging is a good way to test and deploy sensors without logging to internet."
---
## Part 2, Episode 3: Your first Modular Sensors sketch

> ## Prerequisites
>
> - Complete all prior episodes.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 12mm Diameter - 3V Lithium Coin Cell Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), SD card, [DS18B20 Waterproof Digital Temperature sensor and 4.7kΩ resistor](https://www.adafruit.com/product/381), [Grove BME280 Temperature, Pressure, and Humidity sensor](https://www.seeedstudio.com/Grove-Temp-Humi-Barometer-Sensor-BME28-p-2653.html), [Grove I2C hub](https://www.robotshop.com/en/grove-i2c-hub-extension-module.html?gclid=EAIaIQobChMIwfqtttSb3wIVCYZpCh2lhQRgEAQYASABEgI3ifD_BwE), and [Grove cables](https://www.robotshop.com/en/grove-4-pin-buckled-20cm-cable.html).
{: .prereq}

First we will use *simple_logging.ino* to run only the BME280 sensor.
  1. Set up your logger and board settings to give your logger a name, set your time zone, logging interval, and confirm the version of your Mayfly. For now let's select a short logging interval so we can see what's happening on our board.
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_boardsettings.png" width="600">
  2. Comment out lines 67-95 by selecting all of the text for the AOSong and Apogee sensors. To comment out multiple lines at a time, most code editors allow you to select all of the text you wish to comment out and do the following keystroke commands:
      - MacOS: <kbd>Command</kbd>+<kbd>/</kbd>
      - PC and Linux: <kbd>Ctrl</kbd>+<kbd>/</kbd>  
  3. Leave the BME280 sensor (lines 98-105 untouched for now. Following the same procedure as in step 1, comment out the remaining sensors (lines 108-410).
  4. In the variable array, comment out all lines unrelated to the Mayfly or the BME280 as shown:
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_BME280.png" width="600">
  5. In the "Main setup function" section comment out the sonar and modbus serials:
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_modbussonarout.png" width="600">
  6. Return to the BME280 sensor and confirm the sensor address (e.g. 0x77 is Adafruit default and 0x76 is Grove default). Also uncomment the line about I2C power. If you are running multiple I2C devices, only one of the sensors needs to define this power pin location.
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_BME280sensor.png" width="600">
  7. Set up the platformio.ini file in the root directory of your repository (you may need to copy one from LearnEnviroDIYcode). Save the ini file.
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_ini.png" width="600">
  8. Connect the BME280 to the Mayfly, connect the Mayfly to your computer using the USB cable, and turn it on. (Note: Modular Sensors sketches will not run if the SD card is missing.)
  9. Build/compile and upload your sketch.
  10. View your sensor using the serial monitor (note: `serialBaud = 115200`). After the logger is set up, you can push the round, black button near the SD card on the Mayfly to enter sensor testing mode.

**Congratulations you successfully set up your first Modular Sensors sketch!**

Now we will modify your existing *simple_logging.ino* to add the DS18 temperature sensor.
  1. Connect the DS18 sensor to the digital pin of your choice (D5, D7, or D11) following our example in Part 1 Episode 6.
  2. *Turn on* (so... what I mean by *turn on* is to undo the commenting out of this sensor) the *Maxim DS18 One Wire Temperature Sensor* for a sensor with unknown address and assign the pin (called *OneWireBus*):
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_onewire.png" width="600">
  3. Be sure to add this sensor to the variable array as well: `new MaximDS18_Temp(&ds18_u),`.
  4. Save the sketch, compile/build, upload, open the serial monitor, and enter sensor testing mode as soon as you are able.
  5. As you watch the sensor test, notice that Modular Sensors not only figured out how to communicate with your OneWire sensor with unknown address, it found the address for you! As you may have noticed in the sensor block for the DS18, in order to run multiple instances of this sensor, you need to display the address. There are sketches buried deep in the *.piolibdeps folder that will help you find this address, but you can also use the unknown address option in Modular Sensors to find your sensor's address.  


In our next few episodes, we will get learn to set up the EnviroDIY data portal to receive your data. Then we will use a sketch that is nearly identical to *simple_logging.ino* to send data to the portal.  


{% include links.md %}
