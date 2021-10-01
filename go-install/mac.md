# Setup instructions for MacOS

1. Get **MacOS** ready for the Go install by running `xcode-select --install` in terminal. Follow the onscreen prompts to install.

2. Download the latest release of Go for **MacOS** from [here](https://golang.org/dl/).

3. Run and follow the prompts to install Go.

4. Check with shell you are using with `echo $SHELL`. If it is `/bin/bash` open your `.bash_profile` file using `open ~/.bash_profile` in terminal. If it is `/bin/zsh` open your `.zshrc` using `open ~/.zshrc`. If either of these files don't exist create them using `touch ~/.bash_profile` or `touch ~/.zshrc`. Add the following lines to the bottom of the file:

```
export GOPATH="$HOME/go"
export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"
```

5. Save the file and exit.

6. Close and re-open any terminal windows.

7. Verify your installation with the command `go version`. The version needs to be **higher** than `1.13`.
