---
title: "Installing PlatformIO"
teaching: 0
exercises: 45
questions:
- "How will I manage extensive Arduino libraries?"
- "What are the benefits of a code text editor?"
- "How can I easily compare two codes files?"
- "Which buttons do I push in PlatformIO?"
objectives:
- "Download PlatformIO and Atom. Test PlatformIO."
keypoints:
- "PlatformIO provides an Integrated Development Environment (IDE) that combines all the capabilities of the Arduino IDE along with many advanced capabilities of a code editor that you will come to appreciate."
---
## Episode 4: Installing PlatformIO

In this lesson we will prepare you to use PlatformIO, an Integrated Development Environment (IDE) for Internet of Things (IoT). PlatformIO IDE is extremely helpful (and we believe necessary) for keeping track of libraries and code differences when programming a data logger with the EnviroDIY Modular Sensors library. You will install PlatformIO, and become acquainted with many of its features, including file management, syntax highlighting, code difference tracking, code debugging, library management, and integration with Arduino and GitHub.

### Atom and PlatformIO
PlatformIO IDE is hosted within a text editor designed for editing code. Most code text editors highlight syntax and have special auto-complete and debugging features based on elements of the code. PlatformIO can be hosted by several text editors, so if you are a coder and already use VSCode or Sublime, please feel free to install PlatformIO for your favorite editor. The original combination was PlatformIO hosted within Atom text editor. Since Microsoft took ownership of GitHub, their VSCode has become the "recommended" download for PlatformIO, but we continue to use Atom. If you choose a different text editor, some of the buttons and commands will be located in different places, but all of the functionality will be preserved.

- [Install Git](https://git-scm.com/downloads)
  - You need to have an all-purpose Git Client installed to use the library functions in PlatformIO. Although you installed GitHub Desktop, its Git client is only used by that application.
  - Download and install Git from [https://git-scm.com/downloads](https://git-scm.com/downloads). Install selecting all the defaults (make sure your PATH environment allows Git from command line and also from 3rd-party software). We find it best to reboot your computer before installing Atom.

- [Install Atom](https://atom.io/)
  - Download and install official GitHub's Atom text editor, PlatformIO IDE is built on top of it.
  - If you get a **"Clang is not installed on your system!"** message, please proceed to install it.
    - The "Install Clang" button only sends you to the  PlatformIO web page with instructions for installing [Clang for for Intelligent Code Completion](https://docs.platformio.org/en/latest/ide/atom.html#ii-clang-for-intelligent-code-completion). Clang does not install automatically, you need to follow the instructions depending on your operating system.
    - During installation, select **“Add LLVM to the system PATH for all users”** (which is not the default).
    - If you get a "Failed to find MSBuild toolset directory" error when installing on Windows, you can ignore it and conintue, as described [here](https://stackoverflow.com/questions/34029904/problems-installing-clang-in-windows).


- [Install PlatformIO for Atom.](https://platformio.org/install/ide?install=atom)
  - After you install Atom, follow the [PlatformIO for Atom Installation Instructions](https://docs.platformio.org/en/latest/ide/atom.html#installation).
  - In brief, you will go to Settings in Atom (gear symbol), select install (plus symbol) and type in `platformio-ide` in the box that says "search packages" (see image below). PlatformIO should appear in the list after your search. Click on the blue install button and follow any additional instructions (such as to restart) to complete the installation.
  - Installation may take a while, as a lot of dependencies (i.e. other libraries and plugins used by PlatformIo) are also being installed.
  - You may wish to read through the [PlatformIO quick start guide for Atom](https://docs.platformio.org/en/latest/ide/atom.html#quick-start), but our tutorial will take you through many of the same steps.
  - NOTE for Windows users:
    - PlatformIO is written in Python 2.7, which should automatically get installed as a dependency. However, there can be conflicts if you have an existing installation of Python 3.6.x. See https://github.com/platformio/platformio-atom-ide-terminal/issues/668#issuecomment-470893810.

  ![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation002.png)

- You can also choose VSCode instead of Atom
  - Note that all our PlatformIO instructions in this tutorial are geared for Atom.
  - [Install PlatformIO for VSCode](https://platformio.org/install/ide?install=vscode)
  - Follow the instructions to download VSCode, then within VSCode you will use a command line to install PlatformIO.
  - As recommended on the download page, read through the [PlatformIO quick start guide for VSCode](https://docs.platformio.org/en/latest/ide/vscode.html#quick-start).
  - Note: VSCode might recommend that you install the "Arduino" extension for the `.ino` file types. DO NOT do this, as it will conflict with PlatformIO.


### What you can see in PlatformIO
In the following sections we will take you on a tour through the PlatformIO for Atom user interface to describe which features of PlatformIO you will need for using EnviroDIY Modular Sensors sketches.

#### PlatformIO Toolbar:
- For Atom, the PlatformIO Toolbar is on the left side.
- For VSCode, the the PlatformIO Toolbar on the bottom.

![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation003.png)

**PlatformIO Home.** This is where you will manage software updates for PlatformIO and other libraries that PlatformIO sees you using. You will know when updates are needed because they will be marked with bright badges. You also create a PlatformIO account here, which I think you need if you use some of the development capabilities; I don’t have a PlatformIO account.

**Build (checkmark).** Known as “compile” in Arduino. This is the button you push when your sketch is ready and your `platformio.ini` is pointing to all of the right files and repositories for your sketch. This process will list color-coded errors (and successes) as it runs the build. I have found that the error messages are usually pretty understandable and repairable, so don’t despair. Red error messages will not allow you to proceed. Yellow error messages will still allow you to proceed.

**Upload (right arrow).** This is the button that will send your sketch to your Arduino board.

**Upload to remote device (cloud arrow).** I have never used it, but I dream of the day when I can upload to a deployed sensor station!

**Clean (trash can).** This removes previously compiled files and can be helpful to clear any compile errors. The only downside is that it will need to recompile all files, which can take a bit longer to complete.

**Test (flask).** We don't use this.

**Debug (bug).** We don't use this, and it apparently requires a PlatformIO account.

**Run other target (page with checkmark).** We don't use this.

**Toggle Build Panel (vertical arrows).** When you build a sketch and it is successful, the terminal with the build messages disappears. If you want to check out what it said, you can press this and it will bring back your most recent build.

**Find in Project (magnifying glass).** Works as a “Find and Replace” for all the files in your project directory.

**Terminal (cursor box).** Command line access to the functions of PlatformIO. I’ve had to use this when my pushes to GitHub created conflicts.

**Serial Monitor (power plug).** This is your window into what’s happening on your Arduino board. Every time I upload a sketch this is where I see if it’s working correctly.

**Atom Settings (gear wheel).** The main setting that I change is in the `tree-view` package, which is the code that tells Atom how to view your project files. You will want to see hidden files and need go to Settings>Packages>tree-view to uncheck “Hide Ignored Names.” After you build/compile your sketches, PlatformIO will create several items in your root directory, including the Arduino libraries, and sometimes you will need to be able to see these (namely, `.git`, `.pioenvs`, and `.piolibdeps`).

![Source and Destination Files]({{ page.root }}/fig/PlatformIO_navigation004.png)

#### Project tab
This is basically Finder/Windows Explorer conveniently located right in PlatformIO. You can add, move, copy, and delete files and folders in this tab. Right-clicking on any of the items in your project will give you a list of possible actions. I also frequently use the “Copy Project Path” option for naming the source directories in my `platformio.ini` file.

One of the most important things to notice in the project tab is the blue vertical line along the left side of the project tab. This line indicates which project is the active project, meaning that the `platformio.ini` file in the root directory of that project is where PlatformIO will look for build instructions. In the screen shots provided “ModularSensors” is the active project, and all others are inactive.

There’s a little half-circle that appears when your mouse hovers over the project tab that will allow you to hide or show it as needed. This will be useful when you are comparing two sketches side-by-side.

In the next episode, we will start uploading code to the Mayfly!




{% include links.md %}
