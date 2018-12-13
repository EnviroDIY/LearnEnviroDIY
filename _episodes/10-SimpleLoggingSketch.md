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
  8. Build/compile and upload your sketch.
  9. View your sensor using the serial monitor (note: `serialBaud = 115200`). After the logger is set up, you can push the round, black button near the SD card on the Mayfly to enter sensor testing mode.

**Congratulations you successfully set up your first Modular Sensors sketch!**




{% include links.md %}
