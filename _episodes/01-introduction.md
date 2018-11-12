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

This lesson leverages interactive tutorials that are not directly related to environmental monitoring. We have intentionally chosen this approach to acquaint users to the broader world of Arduino format microcontrollers to demonstrate basic Arduino skills, including uploading, running, and modifying sketches; adding sensors; and managing libraries. The Arduino sketches in this module are simple and require a minimal number of libraries to run. We include a short note for each tutorial to help users know how elements of the tutorial will apply to their use of EnviroDIY Modular Sensors for environmental monitoring.

We strongly recommend that you actively participate in the activities in each tutorial because you will need to be comfortable with both physical connectivity to an Arduino and code edits prior to using EnviroDIY Modular Sensors Library.

Arduino Tutorials
Ladyada's Learn Arduino by Limor Fried
https://learn.adafruit.com/series/ladyadas-learn-arduino, lessons 0-2

Lesson 0: A brief history of Arduino. Walks through the anatomy of an Arduino board and how to install the Arduino software. (Skip the part about Codebender software.)

Lesson 1: Walks you through uploading your first program, which is called a "sketch" in Arduino.

Lesson 2: The anatomy of an Arduino sketch and how to change a sketch. This is the core of what you will do with EnviroDIY Modular Sensors.

Adafruit Learn Arduino by Simon Monk
https://learn.adafruit.com/series/learn-arduino, lessons 0, 2, 6.
Get Arduino Uno 3 Ultimate Starter Kit, $44.99, for all additional parts

Lesson 0: A look at all the parts of the starter kit. Describes a breadboard anatomy. (You will be using breadboards to test sensor wiring prior to soldering for your deployments.) Repeats how to install Arduino software, so you can skip that part.

Lesson 2: Uses resistors to change the brightness of an LED light by utilizing a breadboard. Important for understanding resistors, which are required for many environmental sensors. Introduces you to the different pins on the Arduino board. Understanding pins will be important for connecting environmental sensors.

Lesson 6: Adding a button response to the breadboard means sending a digital input back to the Arduino board. In the "Other Things to Do" step you will add a couple of commands to the sketch that will allow you to see your input responses in the "Serial Monitor". We skipped Mr. Monk's initial introduction to the serial monitor in lesson 5 for brevity, so reading his one page on "The Serial Monitor" from lesson 5 would be helpful. We use the serial monitor all the time to see how sensors are responding before deployment.

Arduino Libraries by Tyler Cooper
https://learn.adafruit.com/arduino-tips-tricks-and-techniques/arduino-libraries
Libraries are the software drivers for everything you connect to an Arduino. Stop here first to learn about Arduino libraries, how to use them in a sketch, and the file structures of libraries.

All About Arduino Libraries by Bill Earl
https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use
This lesson teaches you what libraries are and how to manage them, including common problems. It's ideal to understand this fundamental library structure before using PlatformIO to manage your libraries, which is how we will manage an unruly number of libraries when using the EnviroDIY Modular Sensors sketches.

Multi-tasking the Arduino Part 1 by Bill Earl
https://learn.adafruit.com/multi-tasking-the-arduino-part-1
Because an Arduino is a microcontroller and not a computer, it can do only one thing at a time. This means that to perform multiple tasks we need to combine sketches. EnviroDIY Modular Sensors combines many, many functions for you (so you won't have to). We want you to work through this tutorial because it teaches you about class structures, which is the core of how Modular Sensors is structured. Until you are a developer, you will not be combining outside sketches with the EnviroDIY Modular Sensors, but you will need to modify Modular Sensors sketches to run your specific set sensors and to do that you need to recognize constructor functions. (rephrase this for clarity and sequencing)

(RESUME here)
Including intro to object-oriented (class/subclass) structures that are used in complex libraries like ModularSensors, starting with https://learn.adafruit.com/multi-tasking-the-arduino-part-1/a-classy-solution
https://learn.adafruit.com/multi-tasking-the-arduino-part-2

Arduino as a Data Logger platform
4 Lectures in HydroInformatics course by Jeff Horsburgh
https://usu.instructure.com/courses/417249/pages/lecture-materials
4 lectures from Sep. 13-22



{% include links.md %}
