---
title: "Second Sketch: logging_to_EnviroDIY.ino"
teaching: 10
exercises: 20
questions:
- "Where in my sketch do I put UUIDs from data.EnviroDIY?"
- "How do I tell what changes have been made to a sketch?"
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
  2. Open both sketches. With *logging_to_EnviroDIY.ino* as the active tab, right click on *simple_logging.ino*.
  3. In the drop-down menu, select *Diff with Active File*.
  4. Every line with different content will be highlighted in both files. Depending on how well the diff handles comment out characters, you may be able to see that much of the sketches align. However, *logging_to_EnviroDIY.ino* has three major differences that matter for our purposes:
    - a section for modem settings,
    - UUIDs in the variable array, and
    - a section for "registration and sampling feature information".
  5. Let's get out of Split Diff mode. You may do this by closing the tab that you right-clicked on, but I'm not good at remembering that. Instead go to Packages>Split Diff>Toggle (note the keystroke command available in the menu).



{% include links.md %}
