---
title: "Second Sketch: logging_to_MMW.ino"
teaching: 10
exercises: 30
questions:
- "Where in my sketch do I put UUIDs from Monitor My Watershed?"
- "How do I find the changes that have been made to a sketch?"
objectives:
- "Log data to an online repository. Install and use split-diff package."
keypoints:
- "Where to insert UUIDs into Modular Sensors sketches. How to view differences between sketches."
---
## Episode 13: Your second Modular Sensors sketch

> ## Prerequisites
>
> - Complete all prior episodes.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 Lithium Coin Cell 3V Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), SD card, [DS18B20 Waterproof Digital Temperature sensor and 4.7kΩ resistor](https://www.adafruit.com/product/381), [Grove BME280 Temperature, Pressure, and Humidity sensor](https://www.seeedstudio.com/Grove-Temp-Humi-Barometer-Sensor-BME28-p-2653.html), [Grove I2C hub](https://www.robotshop.com/en/grove-i2c-hub-extension-module.html?gclid=EAIaIQobChMIwfqtttSb3wIVCYZpCh2lhQRgEAQYASABEgI3ifD_BwE), and [Grove cables](https://www.robotshop.com/en/grove-4-pin-buckled-20cm-cable.html).
> - You will need a sensor station set up at MonitorMyWatershed.org as described in Episode 12.
> - Additional hardware for this sketch includes a modem (see modem list in [Modular Sensors Wiki](https://github.com/EnviroDIY/ModularSensors/wiki)) and a SIM card (such as from hologram.io).
{: .prereq}

#### One of the advantages of working in a code editor is the ability to compare files within the editor. Before we get started with the sketches, install *split-diff* package to Atom:
  - Go to settings (bottom left, gear icon).
  - Click on **Packages**.
  - Search for **split-diff**.
  - Click Install. (Restart Atom if required.)

#### Compare *logging_to_MMW.ino* and your version of *simple_logging.ino* in which you added sensors.
  - Copy *logging_to_MMW.ino* from your cloned Modular Sensors to your repository.
  - Open both sketches.
  - With *logging_to_MMW.ino* as the active tab, right click on *simple_logging.ino*. In the drop-down menu, select **Diff with Active File**.
  - Every line with different content will be highlighted in each file. Depending on how well the diff handles *comment out* characters, you may be able to see that much of the sketches align. However, *logging_to_MMW.ino* has several major differences that we will unpack so you can edit what you need and ignore what you do not need to change:
    - small differences in the file header and name
    - a massive section for modem settings (~500 lines of code to accommodate nearly any modem you could use with an Arduino),
    - some differences in the sensors,
    - UUIDs in the variable array,
    - a section for "registration and sampling feature information", and
    - lots of extra code in the setup and loop functions.
  - You may wish to exit Split Diff mode by selecting from the menu: **Packages>Split Diff>Toggle** (note the keystroke command available in the menu). I sometimes find this mode helpful to leave on as I make edits to a sketch.

#### Set up *logging_to_MMW.ino* to run BME280 and/or DS18 sensors.
  - In **Data Logger Settings**, edit your sketch name, logger ID, logging interval and time zone.
    ```cpp
      new Modem_RSSI(&modem, "12345678-abcd-1234-efgh-1234567890ab"),
      new Modem_SignalPercent(&modem, "12345678-abcd-1234-efgh-1234567890ab"),
    ```
  - In **Wifi/Cellular Modem Main Chip Selection**, make sure only one modem is uncommented. Recall that commented out lines start with `//`. If you are using the Mayfly, you will not need to make any additional edits to the modem settings.
  - Around line 540, you will find the **Network Information and LoggerModem Object** section. Change the apn to match your SIM provider: `const char *apn = "hologram";` or for WiFi modems, put in the ID and Password.
  - **Sensors**: Beginning around line 566, you should find the sensors. Confirm that they are correctly addressed, as discussed in Episode 10.
  - In the **Variable Array**, copy and paste the tokens and UUIDs from your data.EnviroDIY.org site.
        - This task is tedious. I recommend pasting the UUIDs from your MonitorMyWatershed.org site in the *ReadMe.md* file that was included with *logging_to_MMW.ino*.
        - Then split your screen between the *ReadMe.md* file and your sketch. This is different than split diff; it's simply a split screen without differencing.
        - With *ReadMe.md* and *logging_to_MMW.ino* both open, right click on the tab that is not active and select **Split Left** (or right or up or down).
        - This is my preferred method for pasting UUIDs into a sketch.
  - In the **A Publisher to Monitor My Watershed** section, insert your registration token and sampling feature from your MonitorMyWatershed.org site (this should be among the things you pasted into your *Readme.md* file).  

#### Connect sensors and upload sketch  
  - Set up the platformio.ini file in the root directory of your repository. Save the ini file.  
  - Connect the BME280 and or the DS18 to the Mayfly (as we did in Episodes 6 and 10), connect the Mayfly to your computer using the microUSB cable, and turn it on. (Note: Modular Sensors sketches will not run if the SD card is missing.)  
  - Build/compile and upload your sketch.
  - View your sensor using the serial monitor (note: `serialBaud = 115200`). After the logger is set up, push the round, black button near the SD card on the Mayfly to enter sensor testing mode.
  - Your serial monitor will now include information about your modem signal strength. Sometimes the first few logging intervals have low strength, so watch give the modem a warm up period.  
  - If your modem displays a non-zero signal strength, press the reset button (small, white rectangle near the coin battery and lipo connectors). This will restart the sketch, which allows logging mode to resume. Do not go into sensor testing mode. Wait for logging to begin. If the server response is **201**, you have successfully logged to a data repository!


{% include links.md %}
