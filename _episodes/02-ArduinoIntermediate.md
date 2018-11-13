---
title: "Arduino Intermediate Skills for EnviroDIY"
teaching: 0
exercises: 45
questions:
- "What is an Arduino library and how do I use it?"
- "What intermediate code structures are critical to data logging?"
objectives:
- "Learn how to use external libraries, which leverage the power of C++."
- "Learn how to use a C++ class, using a `constructor` function, leveraging Object Oriented Programming."
- "Learn how Arduinos can multi-task using timing functions."
keypoints:
- "Arduino libraries offer an amazing array of functionality, by providing higher-level functions."
- "Many libraries, including ModularSensors, use Object Oriented Programming, in which a class of objects is defined. A special type of function called a `constructor` creates an object of that class."
---

In **Part 1, Episode 2**, we continue to introduce you to Arduino concepts and skills necessary for utilizing ModularSensors. We again do this through online tutorials.

> ## Actively Participate
> We strongly recommend that you actively participate in the activities in each tutorial because you will need to be comfortable with both physical connectivity to an Arduino and code edits prior to using EnviroDIY Modular Sensors Library.
{: .callout}


## Part 1, Episode 2: Arduino Intermediate Skills for EnviroDIY

**[Arduino Libraries](https://learn.adafruit.com/arduino-tips-tricks-and-techniques/arduino-libraries) by Tyler Cooper**
- Libraries are the software drivers for everything you connect to an Arduino. Stop here first to learn about Arduino libraries, how to use them in a sketch, and the file structures of libraries.

**[All About Arduino Libraries](https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use) by Bill Earl**

- This lesson teaches you what libraries are and how to manage them, including common problems. It's ideal to understand this fundamental library structure before using PlatformIO to manage your libraries, which is how we will manage an unruly number of libraries when using the EnviroDIY Modular Sensors sketches.

**[Multi-tasking the Arduino Part 1](https://learn.adafruit.com/multi-tasking-the-arduino-part-1) by Bill Earl**
- Because an Arduino is a microcontroller and not a computer, it can do only one thing at a time. This means that to perform multiple tasks we need to combine sketches. EnviroDIY Modular Sensors combines many, many things for you (run multiple sensors with different warm up times, putting the sensors to sleep, use solar energy to recharge batteries, save information to an SD card, stream information to an internet portal, etc.).
- This tutorial demonstrates how multitasking sketches handle timing, objects, class, constructors, and functions, which are core of how Modular Sensors is structured. You will need to be familiar with the concepts of object, class, constructor, and function, but you will not need to be able to create any of these on your own to use the Modular Sensors sketches. Also note that the idea of an external button that we can use to interact with the Arduino (and interrupt it) is used in Modular Sensors to initiate a testing mode.

**[Multi-tasking the Arduino Part 2](https://learn.adafruit.com/multi-tasking-the-arduino-part-2) by Bill Earl**
- This lesson is optional. Introduces interrupts, which Modular Sensors uses for pin changes, sleep mode, and sensor testing mode. The primary need for Modular Sensors users from this lesson is to be aware that interrupts are part of the structure of Modular Sensors and they contribute to the ability to perform multiple tasks.


{% include links.md %}
