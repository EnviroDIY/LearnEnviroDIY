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

### Get Mayfly running in PlatformIO

In PlatformIO, click the Home button and in the PlatformIO Home tab, select *Boards*, and in the search bar search for "Mayfly" or "EnviroDIY". Good news! The Mayfly is among the more than 500 boards supported by PlatformIO.

You did not really need to go find the Mayfly, but we lead you there because we want you to see the columns next to the Mayfly. Notice that the Mayfly's platform is "Atmel AVR" and the framework is "Arduino." These are important pieces of information that you will need to include in your PlatformIO.ini file so you can upload code to the Mayfly. If you are using a different microcontroller for this tutorial, you will need to use this information to customize the PlatformIO.ini file to give correct upload instructions for your board.

### Get to know the Mayfly

Many of the Sketches in the EnviroDIY library will not work if the Mayfly is missing an SD card. While we are getting familiar with its ports and connections, let's take a moment to insert a CR1220 coin battery and SD card into the Mayfly. The coin battery keeps the Real Time Clock running on the Mayfly, which we will set at the end of this episode. You will need a separate, external battery to supply power to the Mayfly and sensors.

To insert the coin battery, make sure the positive (+) side of the battery is facing upward as shown below. (Caution: if you insert the battery upside-down you might ruin the Real Time Clock).  
![Source and Destination Files]({{ page.root }}/fig/MayflyBattSD.JPG)

Press the battery securely (and carefully) into the slot on the Mayfly. The fit is intentionally tight, and inserting the battery is somewhat difficult to do. If you need extra leverage, using the edge of the cover on your starter kit (shown below) might give you what you need to push the battery into the slot (but don't push too far!). The good news is that you will not have to do this again for years.
![Source and Destination Files]({{ page.root }}/fig/MayflyBattPush.jpg =600x)

Inserting the SD card is much easier. Orient the card into the SD card slot as shown above and it will set itself with a click. To remove, push the SD card deeper into the slot (gently), and the spring mechanism will release or eject the card.

### Create a project of Episode 5 sketches
[Download Sketches for Part 1 Episode 5](weblink)
You have a few ways to use an existing GitHub repository (repo from now on), including to *fork*, *clone*, or *download* the full repository of files. The typical GitHub behavior is that downloading individual files or folders within a repo is possible but difficult. Let's pause for a moment and find out what each of those actions means.

> ## GitHub Jargon
>**Fork:** If you want to take an existing repo and modify it for your purposes, you could *fork* the repo. That sounds a lot like copying someone else's work, but in the GitHub and open-source world, this is permitted and encouraged. Forking through GitHub retains attribution and authorship. For example, if you look at the documentation for this tutorial, you will see that we are using a repository designed by Software Carpentry.
>
>If you want to make improvements to someone else's repo, you can fork the repo, make your edits, and then do a *pull request* to share it with the owners of the repository, to offer that they *pull* it back into their repository. This type of skills sharing is one of the more powerful aspects of the open source world.
>
>**Clone:** This approach gives you direct access to a repository, and makes the most sense if you have access to contribute to the repository. When we clone a repository, our *Git* software (e.g. GitHub Desktop) will track the history and changes of the repo and allow you to fetch those changes and directly update the files stored on your computer in your project. If you have access to contribute, you can also *push* your changes to the repo.
>
>**Download:** This approach allows you to download and use files from a repo. It will not track changes or allow you to contribute to the repo, but you may edit the files as much as you like. For the purpose of this tutorial, downloading the repo is the best option.
{: .callout}

### Load your first sketch from PlatformIO!

- **Step 1:** Before you download the repo, we recommend that you make a folder dedicated to Arduino, if you haven't already. Locate it somewhere convenient to your file management structure (mine is ~Documents/Arduino/...).

- **Step 2:** We made a dedicated repository for this learning tutorial called [LearnEnviroDIYcode](https://github.com/EnviroDIY/LearnEnviroDIYcode). Go to this GitHub site and click on the green "Clone or Download" button (see below). Select the "Download ZIP" option and save the file in your dedicated Arduino directory. Finally, unzip the download and you will notice that it contains a few directories, including codes for the Arduino Starter Kit for Episodes 1&2, and more.
![Source and Destination Files]({{ page.root }}/fig/GitDownload.png =600x)

- **Step 3:** In PlatformIO, add the unzipped directory as a "Project" by going to File>Add Project Folder... and selecting your *LearnEnviroDIYcode* directory. Notice that each sketch includes a folder that is named identically to the *.ino* file Ardunio sketch. This structure is still required even though we are not working in the Arudino IDE.  

- **Step 4:** Open Blink_Example1_Mayfly.ino, and examine the code. It should look extremely familiar to the very first sketch from Ladyada's lesson 1. We changed the pin number in the sketch to match one of the LED options on the Mayfly. Although many Arduino framework boards have compatible functionality, the ports and lights are usually not located at the same pin numbers. Most have a listing or schematic diagram to help you locate the pin numbers.

- **Step 5:** Open platformio.ini file located in the LearnEnviroDIYcode directory. Notice that opening this ".ini" file caused the *LearnEnviroDIYcode* to be highlighted with the blue vertical line indicating that it is the active directory (if it wasn't already). This is an “initialization” file (the community calls it the “ini” file, pronounced like an innie belly button).

  This file is where you give PlatformIO instructions, and we have it set up for your first sketch. We have it set up with `[env:mayfly]`, and we specified the board and framework you are using (e.g. board = mayfly and framework = arduino), the “lib deps” needed for the sketch, and other information that you will not need to change. The part that you will need to change is the source directory, which is where PlatformIO will look for the Arduino sketch to "Build/Compile" and "Upload", located under `[platformio]`. Currently the source directory is set as `src_dir = Part1Episode5-sketches/Blink_Example1_Mayfly` (in line 12), which is what we want to use as our first sketch.

  Notice line 13 has a different source directory listed, but it has a semicolon (;) at the beginning, which comments out this line. We commonly keep a list of the source directories that we are actively using and add or remove the semicolon to switch between sketches.

> ## Note:
> The platformio.ini file must be located in the root directory for your project. When you start using Modular Sensors, many of the sketches will have a “platformio.ini” file included in the sketch directory; these exist so you do not have to guess which “lib deps” you will need to run the sketch, and not guessing is awesome. But PlatformIO will only look for the ".ini" file in the root of the active directory.
>
>ALSO NOTE: If you are working with a group and syncing to GitHub, you want your root platformio.ini file to be among the files that do not get uploaded to GitHub (list it in the gitignore and/or uncheck it when pushing your contributions to GitHub).
{: .callout}

- **Step 6:** Connect the Mayfly logger using the USB cable included in your starter kit. Turn the Mayfly on. Push the Build/Compile button (checkmark). You should see a terminal pop up and lines of text will scroll through the terminal, and if all goes well, it will conclude with a green bar that says "platform run" and "[SUCCESS]" in green, as shown below.

![Source and Destination Files]({{ page.root }}/fig/platformrunSuccess.png)

- **Step 7:** Upload the sketch to the Mayfly by pushing the right arrow button:
  ![Source and Destination Files]({{ page.root }}/fig/pioUploadButton.png)
  The success indicator will look the same as in Step 6. And the green LED on your Mayfly will blink on and off!
  Notice that you did not have to select your upload port like you did in the Arduino IDE; PlatformIO did this for you.
    -If your upload was not successful, double-check to see if the Mayfly is turned on. Another possibility is that your USB cable, if it did not come with the EnviroDIY kit, is not able to transmit data (some are charging only).

### Load your second sketch!
- **Step 8:** Upload a different sketch to the Mayfly. Go back to the platformio.ini file and type a ";" in front of the "example1" sketch, and uncomment the Blink_Example2_Mayfly sketch to make that active. **Save the platformio.ini file.** Push the Build/Compile button (checkmark), and after that has completed, push the Upload button (right arrow). The Mayfly should blink as it did before, but now we will be able to check its status through the serial monitor by clicking the power plug button:
  ![Source and Destination Files]({{ page.root }}/fig/pioSerialMonitorButton.png)
  You will be prompted to select your Port and Baudrate:
  ![Source and Destination Files]({{ page.root }}/fig/pioPortBaudrate.png =300x)
  The Baudrate is defined in the sketch as 9600.
  Regarding your port selection:
  **In Windows** your port will be `COM?`, where ?=some number (but it won't be `COM1`). Every Arduino board that you plug into your computer will be seen as a completely unique and new piece of hardware, and Windows assigns each a sequentially higher COM number (until it reaches 99, but that's a problem for another day).
  **In MacOS** your port will be a long string of gobbledygook with something about "usb" in the string (as shown above).
  Your serial output should look something like this:
  ![Source and Destination Files]({{ page.root }}/fig/SerialMonitorBlink.png =600x)
  When you are testing sensors in the Modular Sensors sketches, the serial monitor will help you confirm that all of your sensors are working correctly, which is an extremely useful thing.








{% include links.md %}
