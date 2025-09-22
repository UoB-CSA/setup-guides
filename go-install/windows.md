## SYSTEM SETUP FOR WINDOWS 10 or 11

### Windows can now run Linux graphics applications "out of the box". Note that is you have SDL2 graphics working from year 1, jump straight to the [GoLang install instructions](https://github.com/UoB-CSA/setup-guides/blob/master/go-install/windows.md#install-the-correct-version-of-golang) in the first instance

### Ubuntu 24.04 has been tested and works with final coursework

This is a brief tutorial on how to setup your personal Windows 10 or 11 64bit Home or Professional system to be ready for the COMS20008 unit. The below steps represent one out of many ways of setting up your Windows 10 or 11 system for the unit. Before you start make sure Windows 10 or 11 is up-to-date with respect to updates and features. It is your responsibility to keep your personal system and passwords safe.

CHECK SYSTEM COMPATIBILITY
--------------------------

*   Windows search "about" (i.e. hold the Windows key down and simultaneously press "s" so the Windows search bar appears, then type "about" into the search bar).
*   Click "About your PC" in the results and the system specifications window should open.
*   Your system is compatible only if:

*   Your "System type" is "64-bit operating system, x64-based processor".
*   Your system is not in S-Mode and your "Edition" is either "Windows 10 Home" or "Windows 10 Professional" or "Windows 11 Home" or "Windows 11 Professional" without "S Mode". If you need to switch out of S-Mode, follow the instructions on the [Microsoft Support Page](https://support.microsoft.com/en-gb/help/4456067/windows-10-switch-out-of-s-mode).
*   To run graphical Linux applications, you will need **Windows 10 Build 19044+ or Windows 11**. If you have an earlier build, you must update your system by going to "Settings -> Update & Security -> Windows Update", then checking for updates and installing any that are available.

INSTALL WSL2 (WINDOWS SUBSYSTEM FOR LINUX) IN WINDOWS 10 or 11
--------------------------

*    Windows search "PowerShell"
*    Launch PowerShell in administrator mode by right-clicking and pressing "Run as administrator"
*    In a PowerShell terminal, run `wsl --install`
*    Restart your computer
*    In a PowerShell terminal, run `wsl --set-default-version 2`
*    In a PowerShell terminal, run `wsl --install -d Ubuntu-24.04`

*    If you already had WSL installed, run `wsl --update` to make sure it's on the latest version.

*    [Troubleshooting](windows_fixes.md)

INSTALL THE CLANG COMPILER
--------------------------

*   In an Ubuntu terminal, run `sudo apt-get update`
*   In an Ubuntu terminal, run `sudo apt-get install build-essential`
*   In an Ubuntu terminal, run `sudo apt install clang`

INSTALL THE SDL2 DEVELOPMENT PACKAGE
------------------------------------

*   In an Ubuntu terminal, run `sudo apt install libsdl2-dev`

RUNNING THE LINUX DESKTOP AND CHECKING SDL2
-------------------------------------------

*   Download the program [hellosdl.c](https://seis.bristol.ac.uk/~sh1670/hellosdl.c) by typing ` wget https://seis.bristol.ac.uk/~sh1670/hellosdl.c` in an Ubuntu terminal
*   Compile the program in that folder by running `clang -std=c11 -Wall hellosdl.c -I /usr/include/SDL2 -l SDL2 -o hellosdl` , where the 'I' (uppercase i) in `-I /usr/include/SDL2` stands for "Include" and the 'l' (lowercase L) in `-l SDL2` stands for "link".
*   Run the compiled program by running `./hellosdl` - if you see a sky blue window appear then SDL2 is working properly!
*   Note that some parts of the SDL library unfortunately have memory leaks, but there's nothing you can do about them, so don't be alarmed if you see some warnings.

INSTALL THE CORRECT VERSION OF GOLANG
-------------------------------------------

1. Run the following commands in terminal:

```bash
wget https://dl.google.com/go/<Go 1.24.7 Go Version for your CPU>.tar.gz
sudo tar -C /usr/local -xzf <Go 1.24.7 Go Version for your CPU>.tar.gz
```
Note your code must compile with Go 1.17 so do not use language features introduced since then - generics are now allowed for example

2. Open your `.bashrc` file (`~/.bashrc`) in your editor of choice. Add the following lines to the bottom of the file:

```bash
export GOPATH="$HOME/go"
export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"
```

3. Save the file and exit.

4. Close and re-open any terminal windows.

5. Verify your installation with the command `go version`. The version **will be `1.24.7`**.

INSTALL A FILE EXPLORER, A TEXT EDITOR AND A WEB BROWSER
-------------------------------------------

*   File explorer: In an Ubuntu terminal, run `sudo apt install nautilus -y`
*   Text editor: In an Ubuntu terminal, run `sudo apt install gnome-text-editor -y`
    - If that doesn't work, run `sudo apt install gedit -y`
*   Web browser: In an Ubuntu terminal, run `sudo apt-get install firefox -y`

<!-- https://download.jetbrains.com/go/goland-2024.2.1.1.tar.gz -->

INSTALL GOLAND (OR INTELLIJ ULTIMATE)
-------------------------------------------
* Open Firefox **from Ubuntu** by typing `firefox &` in an Ubuntu terminal
* Navigate to https://www.jetbrains.com/go/download/#section=linux **from the Ubunut install of Firefox** and download the .tar.gz
* Unpack the archive to your home directory running `tar -xzf ~/snap/firefox/common/Downloads/goland-2024.2.1.1.tar.gz -C ~/` in an Ubuntu terminal (IDE version will be different)
* Run GoLand by typing ` ~/GoLand-2024.2.1.1/bin/goland.sh &` in an Ubuntu terminal (IDE version will be different)
* Log into your [free JetBrains account](https://www.jetbrains.com/community/education/#students). If GoLand cannot find Firefox, point it here: `/snap/bin/firefox`
