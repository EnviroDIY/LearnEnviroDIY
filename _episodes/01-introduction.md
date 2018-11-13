---
title: "Introduction to Arduino for EnviroDIY"
teaching: 0
exercises: 120
questions:
- "How do I connect to an Arduino board? How do I modify an Arduino sketch? How do I connect sensors?"
objectives:
- "Learn basic Arduino skills, including uploading, running, and modifying sketches; adding sensors; and managing libraries."
keypoints:
- "(Insert when compiled)"
---
Overall goal of this training is to prepare you to use the EnviroDIY Modular Sensors Library for environmental monitoring.

This lesson leverages interactive tutorials that are not directly related to environmental monitoring. We have intentionally chosen this approach to acquaint users to the broader world of Arduino format micro-controllers to demonstrate basic Arduino skills, including uploading, running, and modifying sketches; adding sensors; and managing libraries. The Arduino sketches in this module are simple and require a minimal number of libraries to run. We include a short note for each tutorial to help users know how elements of the tutorial will apply to their use of EnviroDIY Modular Sensors for environmental monitoring.

> ## Actively Participate
> We strongly recommend that you actively participate in the activities in each tutorial because you will need to be comfortable with both physical connectivity to an Arduino and code edits prior to using EnviroDIY Modular Sensors Library.
{: .callout}


## Arduino Tutorials

**[Ladyada's Learn Arduino by Limor Fried](https://learn.adafruit.com/series/ladyadas-learn-arduino)**, lessons 0-2

- [Lesson 0: A Tour of Arduino](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-0).
  - Walks through the anatomy of an Arduino board and how to install the Arduino software. (Skip the part about Codebender software.)
- [Lesson 1: Upload your First Sketch](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-1)
  - Walks you through uploading your first program, which is called a "sketch" in Arduino.
- [Lesson 2: The Parts of Sketch](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-2)
  - The anatomy of an Arduino sketch and how to change a sketch. This is the core of what you will do with EnviroDIY Modular Sensors.


**[Adafruit Learn Arduino by Simon Monk](https://learn.adafruit.com/series/learn-arduino)**, lessons 0, 2, 6  
NOTE: You'll need addition parts from an [Arduino Uno Starter Kit](https://www.amazon.com/gp/product/B00BT0NDB8) or an [Adafruit Metro 328 Starter Pack](https://www.adafruit.com/product/3345).

- [Arduino Lesson 0. Getting Started](https://learn.adafruit.com/lesson-0-getting-started)
  - A look at all the parts of the starter kit. Describes a breadboard anatomy. (You will be using breadboards to test sensor wiring prior to soldering for your deployments.) Repeats how to install Arduino software, so you can skip that part.
- [Arduino Lesson 2. LEDs](https://learn.adafruit.com/adafruit-arduino-lesson-2-leds)
  - Uses resistors to change the brightness of an LED light by utilizing a breadboard. Important for understanding resistors, which are required for many environmental sensors. Introduces you to the different pins on the Arduino board. Understanding pins will be important for connecting environmental sensors.
- [Arduino Lesson 6. Digital Inputs](https://learn.adafruit.com/adafruit-arduino-lesson-6-digital-inputs)
  - Adding a button response to the breadboard means sending a digital input back to the Arduino board. In the "Other Things to Do" step you will add a couple of commands to the sketch that will allow you to see your input responses in the "Serial Monitor". We skipped Mr. Monk's initial introduction to the serial monitor in lesson 5 for brevity, so reading his one page on "The Serial Monitor" from lesson 5 would be helpful. We use the serial monitor all the time to see how sensors are responding before deployment.

**[Arduino Libraries by Tyler Cooper](https://learn.adafruit.com/arduino-tips-tricks-and-techniques/arduino-libraries)**
- Libraries are the software drivers for everything you connect to an Arduino. Stop here first to learn about Arduino libraries, how to use them in a sketch, and the file structures of libraries.

**[All About Arduino Libraries by Bill Earl](https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use)**

- This lesson teaches you what libraries are and how to manage them, including common problems. It's ideal to understand this fundamental library structure before using PlatformIO to manage your libraries, which is how we will manage an unruly number of libraries when using the EnviroDIY Modular Sensors sketches.

**[Multi-tasking the Arduino Part 1 by Bill Earl](https://learn.adafruit.com/multi-tasking-the-arduino-part-1)**
- Because an Arduino is a microcontroller and not a computer, it can do only one thing at a time. This means that to perform multiple tasks we need to combine sketches. EnviroDIY Modular Sensors combines many, many things for you (run multiple sensors with different warm up times, putting the sensors to sleep, use solar energy to recharge batteries, save information to an SD card, stream information to an internet portal, etc.).
- This tutorial demonstrates how multitasking sketches handle timing, objects, class, constructors, and functions, which are core of how Modular Sensors is structured. You will need to be familiar with the concepts of object, class, constructor, and function, but you will not need to be able to create any of these on your own to use the Modular Sensors sketches. Also note that the idea of an external button that we can use to interact with the Arduino (and interrupt it) is used in Modular Sensors to initiate a testing mode.

**[Multi-tasking the Arduino Part 2 by Bill Earl](https://learn.adafruit.com/multi-tasking-the-arduino-part-2)**
- This lesson is optional. Introduces interrupts, which Modular Sensors uses for pin changes, sleep mode, and sensor testing mode. The primary need for Modular Sensors users from this lesson is to be aware that interrupts are part of the structure of Modular Sensors and they contribute to the ability to perform multiple tasks.


{% include links.md %}
