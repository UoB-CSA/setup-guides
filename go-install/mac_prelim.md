SYSTEM SETUP FOR OSX
====================

* Enter: `xcode-select --install` to start the Command Line Developer Tools install dialogue - follow instructions as above.

If that fails, as a last resort install 'Xcode' from the App Store on your Mac.

INSTALL HOMEBREW
----------------

*   In a terminal, run `brew` to check if the [Homebrew](https://brew.sh) package manager is already installed.
*   If a 'command not found' error is shown, run the following command in your terminal and follow the instructions, including the commands it tells you to run in the "Next steps" section after the installation finishes:  
    `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
*   If you encounter a permissions issue on your device you may want to check out this [discussion](https://gist.github.com/irazasyed/7732946).
*   Run: `brew update` (if brew is not added to path - was not on my M1 mac add it:)
*   Edit `~/.zshrc` by typing `open ~/.zshrc` in terminal (or use vim/vscode if you like), add the following lines to the bottom of the file:

   ``` bash
   export PATH="$PATH:/opt/homebrew/bin
   ```
   > **NOTICE:** If your terminal says `The file /Users/your_username/.zshrc does not exist`, you need to type `touch ~/.zshrc` to create the file first.


INSTALL THE SDL2 DEVELOPMENT PACKAGE
------------------------------------

1.  In a terminal, run: `brew install sdl2`
2.  Ensure SDL2 is installed by running: `sdl2-config --version` (version information should be displayed, such as 2.24.0).
3.  Install [pkg-config](https://formulae.brew.sh/formula/pkg-config) to make compiling with SDL2 easier: `brew install pkg-config`

CHECK SDL2 GRAPHICS
-------------------

1.   Install wget by typing `brew install wget`
2.   Download the program [hellosdl.c](https://seis.bristol.ac.uk/~sh1670/hellosdl.c) by typing ` wget https://seis.bristol.ac.uk/~sh1670/hellosdl.c` 
3.  Compile and run the program: `` clang -std=c11 -Wall hellosdl.c -o hellosdl `pkg-config --libs --cflags sdl2` ``
4.  If the compilation was sucessful, you will see the new executable file **hellosdl** in the current directory.
5.  Run this program by running: `./hellosdl`
6.  If you see a sky blue 'HelloSDL' window appear then SDL2 is working properly!
7.  Setup is complete!
8.  Note that some parts of the SDL library unfortunately have memory leaks, but there's nothing you can do about them, so don't be alarmed if you see some warnings.
