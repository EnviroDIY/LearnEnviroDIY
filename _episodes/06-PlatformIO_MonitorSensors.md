---
title: "Using PlatformIO Serial Monitor and Sensors"
teaching: 0
exercises: 90
questions:
- "How do I check the status of my logger in PlatformIO? How do I add sensors to the EnviroDIY Mayfly?"
objectives:
- "Learn the serial monitor. Set real time clock on Mayfly. Connect sensor to Mayfly."
keypoints:
- "Translate additional skills from earlier tutorials using Arduino UNO + Arduino IDE to PlatformIO IDE + EnviroDIY Mayfly logger."
---
> ## Prerequisites
>
> - A computer, an internet connection, and motivation to tinker and hack.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 12mm Diameter - 3V Lithium Coin Cell Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), [DS18B20 Waterproof Digital Temperature sensor and 4.7kΩ resistor](https://www.adafruit.com/product/381), [Grove BME280 Temperature, Pressure, and Humidity sensor](https://www.seeedstudio.com/Grove-Temp-Humi-Barometer-Sensor-BME28-p-2653.html), and an [I2C OLED display with Grove connector](https://www.amazon.com/gp/product/B01D5GLDJ2/).
{: .prereq}

## Part 1, Episode 6: Using PlatformIO

This lesson builds directly on Episode 6. We will interactively explore the features of PlatformIO and finalize your readiness for using the EnviroDIY Modular Sensors sketches in Part 2.

### Load your second sketch from PlatformIO to the Mayfly!
- Open the platformio.ini file in the LearnEnviroDIYcode project and type a ";" in front of the "example1" sketch, and uncomment the Example_02_Mayfly_blink.ino sketch to make that active.
- **Save the platformio.ini file.**
- Push the Build/Compile button (checkmark), and after that has completed, push the Upload button (right arrow).
- The Mayfly should blink as it did before, but now we will be able to check its status through the serial monitor by clicking the power plug button:
  ![Source and Destination Files]({{ page.root }}/fig/pioSerialMonitorButton.png)
  You will be prompted to select your Port and Baudrate:
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/pioPortBaudrate.png" width="400">
  The Baudrate is defined in the sketch as 9600.

  Regarding your port selection:

  **In Windows** your port will be `COM?`, where ?=some number (but it won't be `COM1`). Every Arduino board that you plug into your computer will be seen as a completely unique and new piece of hardware, and Windows assigns each a sequentially higher COM number (until it reaches 99, but that's a problem for another day).

  **In MacOS** your port will be a long string of gobbledygook with something about "usb" in the string (as shown above).
  Your serial output should look something like this:
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/SerialMonitorBlink.png" width="700">
When you are testing sensors in the Modular Sensors sketches, the serial monitor will help you confirm that all of your sensors are working correctly, which is an extremely useful thing.

### Oh hey! There's a sensor on the Mayfly!
- Your next task is to run Example_03_Mayfly_temp. We did not put it in the platformio.ini file for you. Please add it to the "ini" file, save, Build, Upload, and run it on the serial monitor.
  - Notes:
    - You can either type the file name into the "ini" file, or right-click on the directory (not the .ino file!) for Example 3 and select "Copy Project Path" (possibly two-finger click on MacOS, depending on your settings) and paste that into the "ini" file.  
    - The baud rate in the sketch is different and you need to manually select it in your serial monitor.
    - Your serial monitor should be outputting a temperature in degrees C once per second (or 1000 milliseconds).

### Set Real Time Clock on the Mayfly
-


### Connect OneWire sensor: DS18B20 waterproof temperature  



### Connect I2C sensors: BME280 temperature, pressure, and humidity and OLED display


{% include links.md %}
