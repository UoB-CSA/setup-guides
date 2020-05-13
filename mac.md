# Setup instructions for MacOS

1. Get **MacOS* ready for the go install by running `xcode-select --install` in terminal. Follow the onscreen prompts to install.

2. Download the latest release of Go from [here](https://golang.org/dl/).

3. Run and follow the prompts to install Go.

4. Open your `.bashrc` file using `open ~/.bashrc` in terminal. Add the following lines to the bottom of the file.

```
export GOPATH="$HOME/go"
export PATH="$PATH:$GOPATH/bin"
```

5. Save the file and exit.

4. Close and open any terminal windows.

5. Verify your installation with the command `go version`. The version needs to be **higher** the 1.13
