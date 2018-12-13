---
title: "Episode 2.6 Second Sketch: logging_to_EnviroDIY.ino"
teaching: 10
exercises: 30
questions:
- "Where in my sketch do I put UUIDs from data.EnviroDIY?"
- "How do I find the changes that have been made to a sketch?"
objectives:
- "Log data to an online repository. Install and use split-diff package."
keypoints:
- "Where to insert UUIDs into Modular Sensors sketches. How to view differences between sketches."
---
## Part 2, Episode 6: Your second Modular Sensors sketch

> ## Prerequisites
>
> - Complete all prior episodes.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 12mm Diameter - 3V Lithium Coin Cell Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), SD card, [DS18B20 Waterproof Digital Temperature sensor and 4.7kΩ resistor](https://www.adafruit.com/product/381), [Grove BME280 Temperature, Pressure, and Humidity sensor](https://www.seeedstudio.com/Grove-Temp-Humi-Barometer-Sensor-BME28-p-2653.html), [Grove I2C hub](https://www.robotshop.com/en/grove-i2c-hub-extension-module.html?gclid=EAIaIQobChMIwfqtttSb3wIVCYZpCh2lhQRgEAQYASABEgI3ifD_BwE), and [Grove cables](https://www.robotshop.com/en/grove-4-pin-buckled-20cm-cable.html).
> - You will need a sensor station set up at data.EnviroDIY.org as described in Part 2 Episode 4.
> - Additional hardware for this sketch includes a modem (see modem list in *logging_to_EnviroDIY.ino*) and a SIM card (such as from hologram.io).
{: .prereq}

One of the advantages of working in a code editor is the ability to compare files within the editor. Before we get started with the sketches, install *split-diff* package to Atom:
  1. Go to settings (bottom left, gear icon).
  2. Click on **Packages**.
  3. Search for **split-diff**.
  4. Click Install. (Restart Atom if required.)

Compare *logging_to_EnviroDIY.ino* and *simple_logging.ino*.
  1. Copy logging_to_EnviroDIY.ino from your cloned Modular Sensors to your repository (~/Arduino/deployments/tutorials/).
  2. Open both sketches.
  3. With *logging_to_EnviroDIY.ino* as the active tab, right click on *simple_logging.ino*. In the drop-down menu, select *Diff with Active File*.
  4. Every line with different content will be highlighted in each file. Depending on how well the diff handles *comment out* characters, you may be able to see that much of the sketches align. However, *logging_to_EnviroDIY.ino* has three major differences that matter for our purposes:
    - a section for modem settings,
    - UUIDs in the variable array, and
    - a section for "registration and sampling feature information".
  5. Get out of Split Diff mode by closing the tab that you right-clicked on (I'm not good at remembering that) or in the menu select **Packages>Split Diff>Toggle** (note the keystroke command available in the menu).

Set up *logging_to_EnviroDIY.ino* to run BME280 and DS18 sensors.
  1. Use the [simple_logging.ino tutorial](https://envirodiy.github.io/LearnEnviroDIY/10-SimpleLoggingSketch/index.html) to remember what content to comment out (ignore the line numbers). Include the variables related to the modem, even if you are not logging them because they will be useful for debugging:
    ```cpp
      new Modem_RSSI(&modem, "12345678-abcd-1234-efgh-1234567890ab"),
      new Modem_SignalPercent(&modem, "12345678-abcd-1234-efgh-1234567890ab"),
    ```
  2. Copy and paste the tokens and UUIDs from your data.EnviroDIY.org site.
        This task is very tedious. I recommend pasting this information in the ReadMe.md file in (~/Arduino/deployments/tutorials/logging_to_EnviroDIY/). With *logging_to_EnviroDIY.ino* and *ReadMe.md* open, right click on the tab that is not active and select **Split Left** (or right or up or down). This is my preferred method for pasting UUIDs into a sketch.
  3. Change the apn to match your SIM provider: `const char *apn = "hologram";`   
  4. Set up the platformio.ini file in the root directory of your repository. Save the ini file.
  <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/simple_logging_ini.png" width="600">  
  5. Connect the BME280 to the Mayfly, connect the Mayfly to your computer using the USB cable, and turn it on. (Note: Modular Sensors sketches will not run if the SD card is missing.)
  6. Build/compile and upload your sketch.
  7. View your sensor using the serial monitor (note: `serialBaud = 115200`). After the logger is set up, push the round, black button near the SD card on the Mayfly to enter sensor testing mode.
  8. Your serial monitor will now include information about your modem signal strength. Sometimes the first few logging intervals have low strength, so watch give the modem a warm up period.  
  9. If your modem displays a non-zero signal strength, press the reset button (small, white rectangle near the coin battery and lipo connectors). This will restart the sketch, which allows logging mode to resume. Do not go into sensor testing mode. Wait for logging to begin. If the server response is **201**, you have successfully logged to a data repository!


{% include links.md %}
