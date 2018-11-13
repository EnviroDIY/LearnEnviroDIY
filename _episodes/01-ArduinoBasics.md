---
title: "Arduino Basics for EnviroDIY"
teaching: 0
exercises: 120
questions:
- "What are the parts of an Arduino board?"
- "How do I create, upload and modify an Arduino code sketch?"
objectives:
- "Learn basic Arduino skills, including uploading, running, and modifying sketches."
keypoints:
- "Arduino connection, uploading sketches, connecting hardware."
---

In **Part 1: Arduino and IoT for EnviroDIY**, we introduce you to general skills to prepare you for using ModularSensors for environmental monitoring. We do this largely by leveraging interactive online tutorials that are not directly related to environmental monitoring. We have intentionally chosen this approach to acquaint users to the broader world of Arduino-framework micro-controllers.


> ## Actively Participate
> We strongly recommend that you actively participate in the activities in each tutorial because you will need to be comfortable with both physical connectivity to an Arduino and code edits prior to using EnviroDIY Modular Sensors Library.
{: .callout}


## Part 1, Episode 1: Arduino Basics for EnviroDIY

The Arduino sketches in this episode are simple and require a minimal number of libraries to run. We include a short note for each tutorial to help users know how elements of the tutorial will apply to their use of EnviroDIY Modular Sensors for environmental monitoring.

**[Ladyada's Learn Arduino](https://learn.adafruit.com/series/ladyadas-learn-arduino) by Limor Fried**, lessons 0-2

- [Lesson 0: A Tour of Arduino](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-0).
  - Walks through the anatomy of an Arduino board and how to install the Arduino software. (Skip the part about Codebender software.)
- [Lesson 1: Upload your First Sketch](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-1)
  - Walks you through uploading your first program, which is called a "sketch" in Arduino.
- [Lesson 2: The Parts of Sketch](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-2)
  - The anatomy of an Arduino sketch and how to change a sketch. This is the core of what you will do with EnviroDIY Modular Sensors.


**[Adafruit Learn Arduino](https://learn.adafruit.com/series/learn-arduino) by Simon Monk**, lessons 0, 2, 6  
NOTE: You'll need addition parts from an [Arduino Uno Starter Kit](https://www.amazon.com/gp/product/B00BT0NDB8) or an [Adafruit Metro 328 Starter Pack](https://www.adafruit.com/product/3345).

- [Arduino Lesson 0. Getting Started](https://learn.adafruit.com/lesson-0-getting-started)
  - A look at all the parts of the starter kit. Describes a breadboard anatomy. (You will be using breadboards to test sensor wiring prior to soldering for your deployments.) Repeats how to install Arduino software, so you can skip that part.
- [Arduino Lesson 2. LEDs](https://learn.adafruit.com/adafruit-arduino-lesson-2-leds)
  - Uses resistors to change the brightness of an LED light by utilizing a breadboard. Important for understanding resistors, which are required for many environmental sensors. Introduces you to the different pins on the Arduino board. Understanding pins will be important for connecting environmental sensors.
- [Arduino Lesson 6. Digital Inputs](https://learn.adafruit.com/adafruit-arduino-lesson-6-digital-inputs)
  - Adding a button response to the breadboard means sending a digital input back to the Arduino board. In the "Other Things to Do" step you will add a couple of commands to the sketch that will allow you to see your input responses in the "Serial Monitor". We skipped Mr. Monk's initial introduction to the serial monitor in lesson 5 for brevity, so reading his one page on "The Serial Monitor" from lesson 5 would be helpful. We use the serial monitor all the time to see how sensors are responding before deployment.s


{% include links.md %}