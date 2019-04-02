---
title: Setup
---
Do-it-yourself (DIY) enthusiasts generally find rapid success at reading data from simple sensors to an Arduino board. However, it is much more challenging to program an Arduino to perform all required functions of a solar-powered station that collects data from several research-grade environmental sensors, saves to an SD card, transmits to a public server with web services, and puts the sensors to sleep to conserve energy between logging intervals. The [EnviroDIY community](https://www.envirodiy.org/) has made all of this much simpler by creating the [ModularSensors](https://github.com/EnviroDIY/ModularSensors) library, putting the power of the Internet of Things (IoT) revolution into the hands of DIYers.

**These lesson episodes will teach you how to program your Arduino for environmental IoT using [ModularSensors](https://github.com/EnviroDIY/ModularSensors).**

We organize episodes into two parts:
- **Part 1: Arduino and IoT for EnviroDIY (Episodes 1-6)** introduces basic Arduino and IoT skills to prepare you for using ModularSensors.
- **Part 2: Program with ModularSensors (Episodes 7-13)** provides exercises to program, test and deploy a monitoring station based on the example code in the ModularSensors library.

> ## Prerequisites
>
> - A computer, an internet connection, and motivation to tinker and hack.
> - For Episodes 1-2, you'll need an [EnviroDIY Mayfly Data Logger Board](https://www.amazon.com/EnviroDIY-Mayfly-Logger-Arduino-Compatible/dp/B01F9B4WCG/), a [micro-USB cable rated for data](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z),  and a [CR1220 Lithium Coin Cell 3V Battery](https://www.adafruit.com/product/380).
  - Alternately, a [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW) can be a good way to get what you need, plus a nice enclosure and small solar panel (but you would still need the coin battery for the clock and a separate [Lithium Ion Polymer Battery](https://www.adafruit.com/product/1578) for solar powering the board)
  - These tutorials would also work with an [Arduino Uno Starter Kit](https://www.amazon.com/gp/product/B00BT0NDB8), or an [Adafruit Metro 328 Starter Pack](https://www.adafruit.com/product/3345), a [Sparkfun RedBoard Tinker Kit](https://www.sparkfun.com/products/14556), or any Arduino-compatible micro-controller board along with other listed accessories. These starter kits provide additional hardware for fully utilizing existing online tutorials, but these are optional if your focus is to learn Arduino for environmental monitoring.
> - For Episodes 5, 6, 10, & 13, you'll also need:
  - a [DS18B20 Waterproof Digital Temperature sensor and 4.7kΩ resistor](https://www.adafruit.com/product/381),
  - two [Grove screw terminals](https://www.seeedstudio.io/Grove-Screw-Terminal-p-996.html) and included [Grove cables](https://www.seeedstudio.io/Grove---Universal-4-Pin-20cm-Unbuckled-Cable-%285-PCs-Pack%29-p-749.html),
  - a [Grove BME280 Temperature, Pressure, and Humidity sensor](https://www.seeedstudio.com/Grove-Temp-Humi-Barometer-Sensor-BME28-p-2653.html),
  - an [I2C OLED display with Grove connector](https://www.amazon.com/gp/product/B01D5GLDJ2/) (optional), and
  - a [Grove I<sup>2</sup>C hub](https://www.seeedstudio.io/Grove-I2C-Hub-p-851.html) (if you use the OLED display).
{: .prereq}

{% include links.md %}
