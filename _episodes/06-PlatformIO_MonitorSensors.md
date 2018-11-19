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
    - The baud rate in the sketch is different and you need to manually select it when you start the serial monitor.
    - Your serial monitor should be outputting a temperature in degrees C once per second (or every 1000 milliseconds).

> ## Running sketches in PlatformIO
> From this point forward we will not remind you of the steps to upload a sketch, so here they are for quick reference:
> 1. Add your project directory in the src_dir list in platformio.ini and save.
> 2. Build and upload the sketch.
> 3. Run the serial monitor after noting the baud rate for the sketch.
{: .callout}

### Set Real Time Clock on the Mayfly
- We can manually set the Real Time Clock (RTC) on the Mayfly, which will be useful in your future with environmental sensors. Ideally we would let the Mayfly's connection to the WiFi or data network sync the clock, but we will not always have that functionality. As long as your coin battery remains installed and alive, the RTC on your Mayfly will keep ticking.
  1. Setting the RTC is a finicky task.
  2. Upload Example_04_Mayfly_setRTC.ino to your Mayfly.
  3. Open the serial monitor (baudrate 57600) to confirm that it is outputting a time (probably ~January of 2000).
  4. Click on the keyboard icon at the top left corner of the serial monitor window to open the Serial Text Insert box.
  5. Open a web browser to the [current unix time stamp at Sodaq](http://time.sodaq.net/) or http://www.unixtimestamp.com/. I prefer the simplicity of time.sodaq.net.
  6. I like to split my screen between PlatformIO and my web browser for the next task.
  7. As quickly as possible, you will need to copy the numeric unix time from the web browser and paste into the PlatformIO Serial Text Insert box. For the sketch to receive this time it needs to begin with a *T* followed by the numeric unix time stamp. I type the *T* into PlatformIO, then refresh the browser, select the number, copy, insert my cursor after the T in PlatformIO, paste, and immediately press [Enter].
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/serialtextinsert.png" width="400">
  8. If it worked, your serial monitor will begin scrolling a time that is within a minute of the current time, which is good enough for now.

### Connect OneWire sensor: DS18B20 waterproof temperature  
- We


### Connect I2C sensors: BME280 temperature, pressure, and humidity and OLED display


{% include links.md %}
