---
title: "Installing PlatformIO"
teaching: 0
exercises: 20
questions:
- "How will I manage more complicated Arduino code libraries?"
objectives:
- "Download PlatformIO and Atom. Test PlatformIO."
keypoints:
- "PlatformIO is one of many IDEs for code development."
---
## Part 1, Episode 4: Installing PlatformIO

In this lesson we will prepare you to use PlatformIO, an Integrated Development Environment (IDE), which is extremely helpful (and we believe necessary) for keeping track of libraries and code differences when using the EnviroDIY Modular Sensors sketches. You will install PlatformIO, and become acquainted with many of its features, including file management, syntax highlighting, code difference tracking, code debugging, library management, and integration with Arduino and GitHub.

**Atom and PlatformIO**
PlatformIO IDE is hosted within a text editor designed for editing code. Most code text editors highlight syntax and have special auto-complete features based on elements of the code. PlatformIO can be hosted by several text editors, so if you are a coder and already use VSCode or Sublime, please feel free to install PlatformIO for one of these editors. This tutorial will be presented from the perspective of PlatformIO hosted within Atom text editor. Since Microsoft took ownership of GitHub, their VSCode has become the "recommended" download for PlatformIO, but Atom and other editors still work great. If you choose a different text editor, some of the buttons will be located in different places, but all of the functionality will be preserved.

- [Install PlatformIO for Atom.](https://platformio.org/install/ide?install=atom)
  - After you download Atom, as described in the download webpage, you will go to Settings in Atom (gear symbol), select install (plus symbol) and type in `platformio-ide` in the box that says "search packages" to install PlatformIO.

![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation002.png)

### What you can see in PlatformIO

![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation003.png)

#### Left side bar:
**PlatformIO Home.** This is where you will manage software updates for PlatformIO and other libraries that PlatformIO sees you using. You will know when updates are needed because they will be marked with bright badges. Make sure your board is loaded under the Boards sidebar in the Home space (e.g. EnviroDIY Mayfly). You also create a PlatformIO account here, which I think you need if you use some of the development capabilities; I don’t have a PlatformIO account.

**Build (checkmark).** Formerly known as “compile” in Arduino. This is the button you push when your sketch is ready and your platformio.ini is pointing to all of the right files and repositories for your sketch. This process will list color-coded errors (and successes) as it runs the build. I have found that the error messages are usually pretty understandable and repairable, so don’t despair. Red error messages will not allow you to proceed. Yellow error messages will still allow you to proceed.

**Upload (right arrow).** This is the button that will send your sketch to your Arduino board.

**Upload to remote device (cloud arrow).** I have never used it, but I dream of the day when I can upload to a deployed sensor station!

**Clean (trash can).** Harmless to push, and apparently helpful for getting rid of files that are not necessary to keep around. The documentation says it removes compiled files.

**Test (flask).** I haven’t used this.

**Debug (bug).** I haven’t used this, and it apparently requires a PlatformIO account.

**Run other target (page with checkmark).** I haven’t used this.

**Toggle Build Panel (vertical arrows).** When you build a sketch and it is successful, the terminal with the build messages disappears. If you want to check out what it said, you can press this and it will bring back your most recent build.

**Find in Project (magnifying glass).** Works like “Find and Replace” in your word processing app.

**Terminal (cursor box).** Command line access to the functions of PlatformIO. I’ve had to use this when my pushes to GitHub created conflicts.

**Serial Monitor (power plug).** This is your window into what’s happening on your Arduino board. Every time I upload a sketch this is where I see if it’s working correctly.

**Atom Settings (gear wheel).** The main setting that I change is in the “tree-view” package, which is the code that tells Atom how to view your project files. To see hidden files, go to Settings>Packages>tree-view and uncheck “Hide Ignored Names.” After you build/compile your sketches, PlatformIO will create several items in your root directory, including the Arduino libraries, and sometimes you will need to be able to see these (namely, .git, .pioenvs, and .piolibdeps).

![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation004.png)

#### Project tab
This is basically Finder/Windows Explorer conveniently located right in PlatformIO. You can add, move, copy, and delete files and folders in this tab. Right-clicking on any of the items in your project will give you a list of possible actions. I also frequently use the “Copy Project Path” option for naming the source directories in my platformio.ini file.

One of the most important things to notice in the project tab is the blue vertical line along the left side of the project tab. This line indicates which project is the active project, meaning that the platformio.ini file in the root directory of that project is where PlatformIO will look for build instructions. In the screen shots provided “ModularSensors” is the active project, and all others are inactive (even though I am editing files in the LearnEnviroDIY project).



{% include links.md %}
