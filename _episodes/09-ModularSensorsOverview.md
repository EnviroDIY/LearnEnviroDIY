---
title: "Tour of Modular Sensors"
teaching: 20
exercises: 10
questions:
- "How does the Modular Sensors Library meet all of the requirements of data logging? How do I use the Modular Sensors sketches? Why would I clone vs download a repository? Where do I store my own sketches?"
objectives:
- "Download the Modular Sensors Library and become acquainted with its features."
keypoints:
- "Modular Sensors Library features. Cloning vs downloading repository. Using your own repository."
---
The Modular Sensors Library is thoroughly documented on GitHub at the following wiki: [https://github.com/EnviroDIY/ModularSensors/wiki](https://github.com/EnviroDIY/ModularSensors/wiki). This wiki outlines how Modular Sensors works and the sensors that are currently supported. You may refer to this wiki at any time. In this episode we will walk you through the process of getting Modular Sensors sketches ready to run on your system.

We learned in the last [episode on data logging](https://envirodiy.github.io/LearnEnviroDIY/08-DataLogging/index.html) all of the things we need to consider when logging data. Moving from running simple sensor sketches like we did in Part 1 to meeting all of the demands of data logging requires a massive jump in skill level. Modular sensors provides us with a code "wrapper" that is designed to work within the EnviroDIY ecosystem to allow new users the means to log data.

Built into the Modular Sensors Library is the ability to
  run multiple sensors with different warm up times,
  conserve energy (e.g. putting the sensors to sleep),
  use solar energy to recharge batteries,
  save information to an SD card,
  stream information to an internet portal, and
  put all of that functionality together into one sketch because an Arduino framework microcontroller can do one thing at a time.





{% include links.md %}
