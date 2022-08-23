
# Computer Science I
**[School of Computing](https://computing.unl.edu/)**  
**[College of Engineering](https://engineering.unl.edu/)**  
**[University of Nebraska-Lincoln](https://unl.edu)**

This repository stores various resources for helping students enrolled in CSCE155A set up a development environment on their own machine


## Installing Python
In order to run Python scripts on your machine, you must have a stable version installed. You can do this by following the instructions below. First, read the following notes for installing on your operating system (OS)
```
macOS
========
Macs have Python 2 installed and will default to that version. You'll still need to download Python 3 from the website

Windows
========
Check "Add Python 3.x.x to PATH" before clicking install now in the setup wizard. This saves us a step and a lot of possible confusion
```
While keeping the above notes in mind, you can download Python 3 here: https://www.python.org/downloads/

Once the installation is complete, you can verify by opening up your shell and typing the following command exactly as it appears

Windows PowerShell:
```
python --version
```

macOS Terminal:
```
python3 --version
```

Note the difference between the Windows and macOS commands, this is because macOS assumes you are referring to Python 2 if you just type "python". After hitting enter, the shell should output a line listing the version you just installed

```
Python 3.10.6
```

Your version may differ, but if the first digit matches you have successfully installed Python 3!


## Code Editing
The next step is to pick a tool that lets you write and edit source code. This can be done through any plain text editor on your machine like Notepad or TextEdit. Some applications are designed with code editing in mind, and have features that are useful for viewing source code. A few popular code editors can be found below

* Vim (already on macOS) https://www.vim.org/
* VS Code https://code.visualstudio.com/
* Sublime Text https://www.sublimetext.com/
* Atom (being sunset soon) https://atom.io/

We recommend staying away from full-blown IDE's like PyCharm until you are more familiar with development environments


## Basic Unix Commands
A shell allows you to talk to your machine's OS at a much lower level than a graphical user interface (GUI). This gives you more control and lets you make changes to items extremely quickly

Most shells accept commands that are found in Unix and Unix-like environments. These commands allow you to edit files, create directories, change user permissions, and much more. There are a lot of different commands, but some commonly used ones are listed below

```
ls ............. list items in current directory
pwd .......... print current (working) directory
cd <name> ..................... change directory
clear ....... clean up shell by "erasing" output
touch <name> ................ create file (Unix)
New-Item <name> ....... create file (PowerShell)
mkdir <name> .................. create directory
rm <name>................. remove file/directory
```

Many of these these commands will need something called arguments, which let users specify what they would like to happen. Some arguments for the above commands are inside \<>


## Git/GitHub Basics
TODO Give rundown of creating/cloning repos, pushing commits, viewing version history, etc.


## CSE Server Access
TODO Explain use of Secure Message Block, Virtual Private Network, Secure SHell, PuTTY, etc. for accessing files stored on cse server
