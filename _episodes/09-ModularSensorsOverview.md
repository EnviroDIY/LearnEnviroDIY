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

### Clone the repository
To get the files from any public GitHub repo, including Modular Sensors, on your your computer, you have a couple of options. You may download all of the files for the repo, as we did in Part 1, Episode 5 to get the tutorial sketches. But if we want to check for the most current files, we recommend that you "clone" a repo. Since your purpose in this tutorial is to begin your own environmental monitoring, we recommend that you clone the Modular Sensors repo.

To clone Modular Sensors,
  1. Go to the following site: [https://github.com/EnviroDIY/ModularSensors](https://github.com/EnviroDIY/ModularSensors)
  2. Click on the green "Clone or download" button
  3. Select "Open in Desktop" (confirm to "Open GitHub Desktop.app")
  4. A dialogue box will appear in GitHub Desktop where you can indicate where you want to put the files.
  (e.g. I keep all of my Arduino work in a folder by that name located in my root directory /~Documents/Arduino/...)

### Repository branches
Modular Sensors repo is still new and is being regularly modified and improved with new or refined features. Developers add and test new features in different branches of the repository. At any given time, the branches will look something like the image below:
<img src="https://envirodiy.github.io/LearnEnviroDIY/fig/ModularSensorsNetwork.png " width="400">

Notice in this image that an individual is working on their own branch of Modular Sensors. The way GitHub is structured, anyone can copy a repository and modify their copy. In much of society, this level of transparency and sharing is unusual. In the GitHub world this kind of activity is encouraged and regarded as a strength of the platform. When a repo is forked, the attribution of all original contributors is retained. Users who modify the fork can offer to merge their features back into the original repo (through a "pull request"), offering improvements and development capacity that the original team may not have considered or had time to contribute.  

You can easily switch between which branch is saved on your computer in GitHub Desktop by changing the "Current Branch" selection (this may not be a good thing if you change it unintentionally!). "Master" is the default branch for the Modular Sensors repo, and is considered to be the place were features have been tested and are ready for use.

### Managing your own sketches
You just cloned a repository that we want to watch for updates, but you do not have access to send edits back to this repo. Also, you will be editing the sketches from the Modular Sensors repo for your own sensor stations, which may result in your files getting overwritten when you pull updates or "Fetch origin" from GitHub. For all of these reasons, we recommend that you create a new repository for your own sketches.

- Create a new repository and name it *deployments* in your GitHub account as you did in the [GitHub Hello World tutorial](https://guides.github.com/activities/hello-world/#repository). For now we will make this a public repository, but if you may need to consider using a private repo for your organization's deployment sketches.

- Clone your *deployments* repo (as we did earlier in this episode) and make it a project in PlatformIO (as in Part 1 Episode 5).

- Typically within a deployments repo, we keep a separate folder for each project or site. In your *deployments* project in PlatformIO, right click on the *deployments* folder and select "New Folder" from pop up menu. Name the new folder *tutorials*.

- Copy the *simple_logging* sketch from ~/ModularSensors/examples/ by right-clicking on the *simple_logging* folder. Paste this folder into the tutorials folder in your repository (~/Arduino/deployments/tutorials/). Now you can edit this sketch and save your edits to you own repository.

### Anatomy of Modular Sensors Sketches
Open your copy of *simple_logging.ino*. This sketch is 580 lines long with multiple sections. We will give you a what you need to know for each section.

- **Header (lines 1-16)** Comments about the authors and purpose of the sketch. You may add your own deployment notes in this section, but we generally leave the other attribution information intact.

- **Include statements (18-23)** Calls all of the libraries needed to run the sketch. You still need to make sure your platformio.ini file has all of the necessary lib_deps. If you have compile errors, comparing the include statements in the sketch to your platformio.ini file may be helpful.

- **Logger settings (26-37)** This is where you set your logging interval (e.g. 15 minutes), your time zone (Central is UTC -6, and we always stay in standard time). You will rename the sketch to match your sketch name for deployments. In the LoggerID space, we usually include a string that indicates the site name, the logger type, and the logger serial number (e.g. Pond05_Mayfly_321456). Keeping these in good form can aid in parsing data from multiple sites.

- **Board and processor settings (40-56)** The default in the EnviroDIY ecosystem is for the Mayfly logger. However, if you are using a different board, you may enter the pin locations for the LEDs, button, and SD card in this section.

- **Real Time Clock (59-64)** Technically this is the beginning of the list of sensors, but this one is the real time clock (RTC) on the Mayfly, and the Maxim DS3231 is the RTC most commonly in use in the Arduino world. The RTC has a temperature sensor that we are able to log to monitor the temperature of the Mayfly.

- **Massive list of sensors (67-410)** This next section lists nearly all of the sensors currently available in the Modular Sensor Library. The default is for all of the sensors to be *live* in the unedited sketch. Please do not let this give you the impression that you can run all of these at once! When you set up the sketch for your sensors, you will *comment out* the lines that you do not need. The *comment out* character is two forward slashes '//'. To comment out multiple lines at a time, most code editors allow you to select all of the text you wish to comment out and do the following keystroke commands:
    - MacOS: <kbd>Command</kbd>+<kbd>/</kbd>
    - PC and Linux: <kbd>Ctrl</kbd>+<kbd>/</kbd>  

- **Variable Array (413-496)** This is a list of all of the possible variables available to the sensors listed in the sketch. Notice that some sensors have multiple variables. For example, the BME280 that you used in Part 1 Episode 6 includes four variables:
        - new BoschBME280_Temp(&bme280),
        - new BoschBME280_Humidity(&bme280),
        - new BoschBME280_Pressure(&bme280),
        - new BoschBME280_Altitude(&bme280),
As we did for the list of sensors, we will select and comment out the lines we are not using from the variable array. In some cases we will not log all of the variables that are available on a sensor.

- **Working Functions (499-515)** We do not need to change anything in this section. This part of the sketch lights LEDs on the logger board to indicate when the logger is running (in contrast to in sleep mode).

- **Main Setup Function (518-569)** If you are not using a modbus sensor, comment out the following lines:
    - `// Start the stream for the modbus sensors`
    - `modbusSerial.begin(9600);`  

    Similarly, if you are not using a Maxbotix sonar sensor, comment out the following lines:  
    - `// Start the SoftwareSerial stream for the sonar`  
    - `sonarSerial.begin(9600);`  

- **Main loop function (572-579)** No need to change this.

In the next episode, we will set up this sketch and run some sensors!

{% include links.md %}
