---
title: "Arduino Intermediate Skills for EnviroDIY"
teaching: 0
exercises: 120
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

> ## Prerequisites
>
> - A computer, an internet connection, and motivation to tinker and hack.
> - For this episode, you'll need an [EnviroDIY Mayfly Data Logger Board](https://www.amazon.com/EnviroDIY-Mayfly-Logger-Arduino-Compatible/dp/B01F9B4WCG/) and a [micro-USB cable rated for data](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z), because we will use the LEDs and button onboard the Mayfly for the tutorials.
{: .prereq}

In **Episode 2**, we continue to introduce you to Arduino concepts and skills necessary for utilizing ModularSensors. We again do this through online tutorials.

> ## Actively Participate
> We strongly recommend that you actively participate in the activities in each tutorial because you will need to be comfortable with both physical connectivity to an Arduino and code edits prior to using EnviroDIY Modular Sensors Library.
{: .callout}


## Episode 2: Arduino Intermediate Skills for EnviroDIY

**[Arduino Libraries](https://learn.adafruit.com/arduino-tips-tricks-and-techniques/arduino-libraries) by Tyler Cooper**
- Libraries are the software drivers for everything you connect to an Arduino. Stop here first to learn about Arduino libraries, how to use them in a sketch, and the file structures of libraries. You may stop after the first linked page on libraries (skip the information about bootloader and beyond).

**[All About Arduino Libraries](https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use) by Bill Earl**
- This lesson teaches you what libraries are and how to manage them, including common problems. It's ideal to understand this fundamental library structure before using PlatformIO to manage your libraries, which is how we will manage an unruly number of libraries when using the EnviroDIY Modular Sensors sketches.

**[Multi-tasking the Arduino Part 1](https://learn.adafruit.com/multi-tasking-the-arduino-part-1) by Bill Earl**
- You will use the LEDs and button that are onboard the Mayfly for this tutorial.
- Because an Arduino is a microcontroller and not a computer, it can do only one thing at a time. This means that to perform multiple tasks we need to combine sketches. EnviroDIY Modular Sensors combines many, many things for you (run multiple sensors with different warm up times, putting the sensors to sleep, use solar energy to recharge batteries, save information to an SD card, stream information to an internet portal, etc.).
- This tutorial demonstrates how multitasking sketches handle timing, objects, class, constructors, and functions, which are core of how Modular Sensors is structured. You will need to be familiar with the concepts of object, class, constructor, and function, but you will not need to be able to create any of these on your own to use the Modular Sensors sketches. Also note that the idea of an external button that we can use to interact with the Arduino (and interrupt it) is used in Modular Sensors to initiate a testing mode.
- Note, you may test any of these sketches by saving or pasting them into a new sketch and changing the LED pin from `13` to `8` for the Mayfly's green LED2.
- When you need a second LED, use the Mayfly's red LED1 on pin 9.
- When you need a third LED, use the Mayfly's other red LED3 on pin 22. Make sure all three lights are blinking at this stage, or there's something wrong with your code.
- Try to blink all three LEDs using the first stage of multitasking and then using the Object Orienting Programming example.
- Skip the servo motor examples, but continue to the button user input part of the tutorial.
- The Mayfly has a button on pin 21 that you will use to activate sensor testing mode in Modular Sensors. For this tutorial we will program the button to activate one of the LEDs when pressed (and held). To program this, we have to add a simple "if" statement in the loop. Change your `void loop()` to the following:

```C++
void loop()
{
  if(digitalRead(21) == HIGH)
  {
     led1.Update();
  }

  led2.Update();
  led3.Update();
}
```
- Did you notice that the button-triggered LED will stay HIGH if it is HIGH when you release the button?
- Don't forget to go back and read Bill Earl's conclusion page for this tutorial!  

> ## Solution
> The solutions to the advanced blink sketches are hidden in the [LearnEnviroDIYcode  repository](https://github.com/EnviroDIY/LearnEnviroDIYcode). You will be downloading the entire repository in Eposode 1.5, but if you want to check your work here are the solutions:
>  - [Blink without using delay](https://github.com/EnviroDIY/LearnEnviroDIYcode/blob/master/Part1-sketches/Extras/Solution01_ep1-2_blinkwithoutdelay/Solution01_ep1-2_blinkwithoutdelay.ino)
>  - [Blink all three lights using classes](https://github.com/EnviroDIY/LearnEnviroDIYcode/tree/master/Part1-sketches/Extras/Solution02_ep1-2_threeblinkclasses)
>  - [Blink three lights using classes and button interrupt](https://github.com/EnviroDIY/LearnEnviroDIYcode/tree/master/Part1-sketches/Extras/Solution03_ep1-2_threeblinkclasses_button)
{: .solution}


> ## Learning Resources
> - As you dive deeper into Arduino programming, you might want to have these references handy and open in a separate tab to look up the details on any code element that you come across:
>   - [Arduino Language Reference](https://www.arduino.cc/reference/en/)
>   - [Variables Tutorial](https://www.arduino.cc/en/Tutorial/Variables)
>   - [Functions Tutorial](https://www.arduino.cc/en/Reference/FunctionDeclaration)
> - There are many other Arduino learning resources online. Googling code snippets will soon become your friend!
{: .callout}

{% include links.md %}
