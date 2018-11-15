---
title: "Using PlatformIO Serial Monitor and Sensors"
teaching: 0
exercises: 90
questions:
- "How do I check the status of my logger in PlatformIO? How do I add sensors to the EnviroDIY Mayfly?"
objectives:
- "Learn the serial monitor. Connect sensors to Mayfly. Set real time clock on Mayfly. Connect sensor to Mayfly."
keypoints:
- "Translate skills from earlier tutorials using Arduino UNO and Arduino IDE to a new PlatformIO IDE and the EnviroDIY Mayfly logger."
---
> ## Prerequisites
>
> - A computer, an internet connection, and motivation to tinker and hack.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 12mm Diameter - 3V Lithium Coin Cell Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), and selected environmental sensors (list coming soon).
{: .prereq}

## Part 1, Episode 6: Using PlatformIO

In this lesson builds directly on Episode 6. we will interactively explore the features of PlatformIO and finalize your readiness for using the EnviroDIY Modular Sensors sketches in Part 2.

### Load your second sketch from PlatformIO to the Mayfly!
- Open the platformio.ini file in the LearnEnviroDIYcode project and type a ";" in front of the "example1" sketch, and uncomment the Blink_Example2_Mayfly sketch to make that active.
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








{% include links.md %}
