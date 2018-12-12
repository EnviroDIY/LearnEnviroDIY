---
title: "Overview of Datalogger Workflow"
teaching: 20
exercises: 0
questions:
- "Why is the ModularSensors library necessary, and how does it make it easier to program a data logger?"
objectives:
- "Learn the basic steps of a data logging cycle."
keypoints:
- "FIXME"
---


## Part 2, Episode 8: Using PlatformIO

DIYers generally find rapid success at reading data from simple sensors to an Arduino board. However, it is much more challenging to program an Arduino to perform all required functions of a solar-powered station that collects data from several research-grade environmental sensors, saves to an SD card, transmits to a public server with web services, and puts the sensors to sleep to conserve energy between logging intervals. The [EnviroDIY](https://www.envirodiy.org/) [ModularSensors](https://github.com/EnviroDIY/ModularSensors) library was designed coordinate these tasks.

Let's dig in study the various steps of a data logging cycle, along with additional things a data logger needs to do.

### Timing, Sleep and Wake
A datalogger needs to carefully keep track of time for a wide variety of purposes:
- **Logging interval(s)**, or *time spacing*, between recording measurements.
  - Keeping track of logging intervals is complicated by the need to align logging to time stamps on a real time clock, which is a separate device from the micro-controller chip, and the imperative to put the logger into a deep, power-saving sleep mode between recording measurements.
  - Sometimes it is useful for a single datalogger to log different measurements at different intervals.
- **Sensor warm up time**, before it can start sending data or receiving commands after it is powered up.
- **Sensor stabilization time**, before it can start providing reliably stable or precise data after it is powered up.
- **Sensor measurement time**, which is how long the sensor takes to make a single measurement before it can make another.
- **Sensor number of readings**, which is how many individual measurements get made, one after another, to then be averaged for the recorded result for that logging interval.
  - Most sensors benefit from averaging multiple readings, to reduce signal noise. Many commercial sensors with built-in dataloggers, do this by default.
- **Sensor time averaging**, or *time support*, is the product of measurement time and number of readings.
     - Sometimes it is useful to average over a long-enough time to average the effects of real environmental variability.

     <img src="https://envirodiy.github.io/LearnEnviroDIY/fig/TimeScaleTriplet-Horsburg.png" width="400">
Figure from Jeff Horsburgh's lecture 7 in his [2016 HydroInformatics (USU CEE-6110)](https://usu.instructure.com/courses/417249/pages/lecture-materials) class.

### Collecting Data from Various sensors

### Writing Data to an SD Card

### Transmitting Data via Radio

### Debugging



{% include links.md %}
