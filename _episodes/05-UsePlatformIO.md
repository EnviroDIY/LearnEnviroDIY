---
title: "Using PlatformIO and Mayfly"
teaching: 0
exercises: 90
questions:
- "How do I tell PlatformIO which Arduino I am using? How do I use PlatformIO to upload a sketch to an Arduino board? How do I view and edit sketches in PlatformIO?"
objectives:
- "Install Mayfly data logger in PlatformIO. Edit and upload sketches to Mayfly. Set real time clock on Mayfly. Connect sensor to Mayfly."
keypoints:
- "Translate skills from earlier tutorials on Arduino UNO to a new IDE and different logger board."
---
> ## Prerequisites
>
> - A computer, an internet connection, and motivation to tinker and hack.
> - For this episode, you'll need an [EnviroDIY Mayfly Starter Kit](https://www.amazon.com/EnviroDIY-Mayfly-Arduino-Compatible-Starter/dp/B01FCVALDW), a [CR1220 12mm Diameter - 3V Lithium Coin Cell Battery](https://www.adafruit.com/product/380) (also available where watch batteries are sold), and selected environmental sensors (list coming soon).
{: .prereq}

## Part 1, Episode 5: Using PlatformIO

In this lesson we will interactively explore the features of PlatformIO and finalize your readiness for Part 2, where we begin using the EnviroDIY Modular Sensors sketches to run multiple environmental sensors in a manner that is energy efficient and that can send data to an internet repository.

**Get Mayfly running in PlatformIO**

In PlatformIO, click the Home button and in the PlatformIO Home tab, select *Boards*, and in the search bar search for "Mayfly" or "EnviroDIY". Good news! The Mayfly is among the more than 500 boards supported by PlatformIO.

You did not really need to go find the Mayfly, but we lead you there because we want you to see the columns next to the Mayfly. Notice that the Mayfly's platform is "Atmel AVR" and the framework is "Arduino." These are important pieces of information that you will need to include in your PlatformIO.ini file so you can upload code to the Mayfly. If you are using a different microcontroller for this tutorial, you will need to use this information to customize the PlatformIO.ini file to give correct upload instructions for your board.

**Get to know the Mayfly**

Many of the Sketches in the EnviroDIY library will not work if the Mayfly is missing an SD card. While we are getting familiar with its ports and connections, let's take a moment to insert a CR1220 coin battery and SD card into the Mayfly. The coin battery keeps the Real Time Clock running on the Mayfly, which we will set at the end of this episode. You will need a separate, external battery to supply power to the Mayfly and sensors.

To insert the coin battery, make sure the positive (+) side of the battery is facing upward as shown below. (Caution: if you insert the battery upside-down you might ruin the Real Time Clock).  
![Source and Destination Files]({{ page.root }}/fig/MayflyBattSD.JPG)

Press the battery securely (and carefully) into the slot on the Mayfly. The fit is intentionally tight, and inserting the battery is somewhat difficult to do. If you need extra leverage, using the edge of the cover on your starter kit (shown below) might give you what you need to push the battery into the slot (but don't push too far!). The good news is that you will not have to do this again for years.
![Source and Destination Files]({{ page.root }}/fig/MayflyBattPush.jpg)

Inserting the SD card is much easier. Orient the card into the SD card slot as shown above and it will set itself with a click. To remove, push the SD card deeper into the slot (gently), and the spring mechanism will release or eject the card.

**Download sketches for this Episode**
[Sketches for Part 1 Episode 5](weblink)



- [Install PlatformIO for Atom.](https://platformio.org/install/ide?install=atom)
  - After you download Atom, as described in the download webpage, you will go to Settings in Atom (gear symbol), select install (plus symbol) and type in `platformio-ide` in the box that says "search packages" to install PlatformIO.

  Logging to EnviroDIY sketch
  Let’s look at our first sketch: logging_to_EnviroDIY.ino. Before you download this sketch from GitHub, designate a directory on your computer for this Arduino project (e.g. ~/Arduino/Monitoring). Download the three files contained at (https://github.com/EnviroDIY/ModularSensors/tree/master/examples/logging_to_EnviroDIY), namely logging_to_EnviroDIY.ino, platformio.ini, and ReadMe.md. If you choose to clone the Modular Sensors repository, I still recommend creating a new project directory because you will not have access to push edits back to the EnviroDIY repository on GitHub and your personal edits will make it messy for you to pull updates from that repository.

  The .ino file is the Arduino sketch, and it must be in a folder with the same name, so make a folder and put all three files into that folder (~/Arduino/Monitoring/logging_to_EnviroDIY).

  You won’t really need the ReadMe.md file, which is a GitHub “markdown” file that is best viewed online, but as a best practice you can add to this Read Me with your own notes and metadata about your project. Things to keep here include sensor addresses (when applicable), notes on the libraries required for the sketch, UUIDs, the location of the sensor station, etc.
  PlatformIO Initialization file
  The platformio.ini file is an “initialization” file (I call it the “ini” file, pronounced like an innie belly button). This file is where you give PlatformIO instructions, which includes the directory of the sketch you want to upload, the board and framework you are using (e.g. board = mayfly and framework = arduino), the “lib deps” needed for the sketch, and other information that I haven’t had to worry about. The platformio.ini file is located in the root directory for your project. Don’t confuse this with the “ini” files that are included in the directory for each example sketch in the Modular library; these exist so you do not have to guess which “lib deps” you will need to run the sketch, and not guessing is awesome. If you are working with a group and syncing to GitHub, you want your root platformio.ini file to be among the files that do not get uploaded to GitHub (list it in the gitignore).
  Projects in PlatformIO
  In PlatfiormIO under the File menu, select Add Project Folder, and navigate to your ~/Arduino/Monitoring/logging_to_EnviroDIY directory. You should now see this directory among your lists of projects in the left column of your window. Open all three of the files in your directory by double-clicking on them, and they will appear as tabs in the right column of your window.


{% include links.md %}
