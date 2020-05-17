# Setup instructions for the University Linux machines

To setup **Go** for your user account on a **lab machine** you need to update your `.bashrc` file.

1. To open the file use `gedit ~/.bashrc` in terminal.

2. Add this to the end of the file:

```
module load go/1.13
export GOPATH="$HOME/go"
export PATH="$PATH:$GOPATH/bin"
```

3. Save the file and exit.

4. Close and open any terminal windows. (If you are working over **ssh** you can use the command `source ~/.bashrc`)

5. Verify your installation with the command `go version`. The version **must be `1.13`**.
