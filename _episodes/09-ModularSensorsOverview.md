---
title: "Tour of Modular Sensors Library"
teaching: 20
exercises: 10
questions:
- "How does the Modular Sensors Library meet all of the requirements of data logging? How do I use the Modular Sensors sketches? Why would I clone vs download a repository? Where do I store my own sketches?"
objectives:
- "Download the Modular Sensors Library and become acquainted with its features."
keypoints:
- "Modular Sensors Library features. Cloning vs downloading repository. Using your own repository."
---
## Part 2, Episode 2: Tour of Modular Sensors Library

The Modular Sensors Library is thoroughly documented on GitHub at the following wiki: [https://github.com/EnviroDIY/ModularSensors/wiki](https://github.com/EnviroDIY/ModularSensors/wiki). The wiki outlines how Modular Sensors works and the sensors that are currently supported. You may refer to this wiki at any time. In this episode we will walk you through the process of getting Modular Sensors sketches ready to run on your system.

We learned in the last [episode on data logging](https://envirodiy.github.io/LearnEnviroDIY/08-DataLogging/index.html) all of the things we need to consider when logging data. Moving from running simple sensor sketches like we did in Part 1 to meeting all of the demands of data logging requires a massive jump in skill level. Modular sensors provides us with a code "wrapper" that is designed to work within the EnviroDIY ecosystem to allow new users the means to log data.

Built into the Modular Sensors Library is the ability to
  run multiple sensors with different warm up times,
  conserve energy (e.g. putting the sensors to sleep),
  use solar energy to recharge batteries,
  save information to an SD card,
  stream information to an internet portal, and
  put all of that functionality together into one sketch because an Arduino framework microcontroller can do one thing at a time.

#### Clone the repository
To get the files from any public GitHub repo, including Modular Sensors, on your your computer, you have a couple of options. You may download all of the files for the repo, as we did in Part 1, Episode 5 to get the tutorial sketches. But if we want to check for the most current files, we recommend that you "clone" a repo. Since your purpose in this tutorial is to begin your own environmental monitoring, we recommend that you clone the Modular Sensors repo.

To clone Modular Sensors,
  1. Go to the following site: [https://github.com/EnviroDIY/ModularSensors](https://github.com/EnviroDIY/ModularSensors)
  2. Click on the green "Clone or download" button
  3. Select "Open in Desktop" (confirm to "Open GitHub Desktop.app")
  4. A dialogue box will appear in GitHub Desktop where you can indicate where you want to put the files.
  (e.g. I keep all of my Arduino work in a folder by that name located in my root directory /~Documents/Arduino/...)

#### Repository branches
Modular Sensors repo is still new and is being regularly modified and improved with new or refined features. Developers add and test new features in different branches of the repository. At any given time, the branches will look something like the image below:
<img src="https://envirodiy.github.io/LearnEnviroDIY/fig/ModularSensorsNetwork.png " width="400">

Notice in this image that an individual is working on their own branch of Modular Sensors. The way GitHub is structured, anyone can copy a repository and modify their copy. In much of society, this level of transparency and sharing is unusual. In the GitHub world this kind of activity is encouraged and regarded as a strength of the platform. When a repo is forked, the attribution of all original contributors is retained. Users who modify the fork can offer to merge their features back into the original repo (through a "pull request"), offering improvements and development capacity that the original team may not have considered or had time to contribute.  

You can easily switch between which branch is saved on your computer in GitHub Desktop by changing the "Current Branch" selection (this may not be a good thing if you change it unintentionally!). "Master" is the default branch for this repo, and is considered to be the place were features have been tested and are ready for use.

#### Managing your own sketches
We just cloned a repository that we want to watch for updates, but we do not have access to send our edits back to this repo. Also, you will be editing the sketches from the Modular Sensors repo for your own sensor stations. Editing the sketches in this original file may result in them getting overwritten when you pull updates or "Fetch origin" from GitHub. 

#### Anatomy of Modular Sensors Sketches



{% include links.md %}
