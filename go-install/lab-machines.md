# Setup instructions for the University Linux machines

To setup Go for your user account on a **lab machine** you need to update your `.bashrc` file.

1. Open the file by running `gedit ~/.bashrc` in terminal (if you are not in a graphical environment, use a terminal-based editor e.g. `nano ~/.bashrc`).

2. Add this to the end of the file:

```
module load go/1.13
export GOPATH="$HOME/go"
export PATH="$PATH:$GOPATH/bin"
```

3. Save the file and exit.

4. Close and re-open any terminal windows. If you are working over `ssh` you can use the command `source ~/.bashrc`.

5. Verify your installation with the command `go version`. The version **will be `1.13`**.

# Using IntelliJ with go plugin on lab machines

IntelliJ is installed on thr lab machines. To use it, open a terminal an type:

```bash
/opt/idea/idea-IU-212.5080.55/bin/idea.sh &
```

It's just been installed so we have had little time for testing. It should "find" go automatically and configure itself. It may locate a later version of go than that specified above (1.15.14). This is untested with this year's crousework, but should work. If you want to specify the above version, select:
* File->Settings->Languages & Frameworks->Go->GOROOT

and edit appropriately.
