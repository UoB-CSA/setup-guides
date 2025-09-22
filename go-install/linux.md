# Personal Linux setup instructions

## Option 1: Setup instructions for most Linux installations

1. Run the following commands in terminal:

```bash
wget https://dl.google.com/go/go1.17.13.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.17.13.linux-amd64.tar.gz
```

2. Open your `.bashrc` file (`~/.bashrc`) in your editor of choice. Add the following lines to the bottom of the file:

```bash
wget https://dl.google.com/go/<Go 1.24.7 Go Version for your CPU>.tar.gz
sudo tar -C /usr/local -xzf <Go 1.24.7 Go Version for your CPU>.tar.gz
```
Note your code must compile with Go 1.17 so do not use language features introduced since then - generics are not allowed for example

3. Save the file and exit.

4. Close and re-open any terminal windows.

5. Verify your installation with the command `go version`. The version **will be `1.24.7`**.

## Option 2: Setup instructions for Arch Linux

1. Run the following commands in terminal. If bash is not your default shell, substitute `.bashrc` for the appropriate file (e.g. `.zshrc` for zsh).

```bash
sudo pacman -S go
echo 'export GOPATH="$HOME/go"' >> ~/.bashrc
echo 'export PATH="$PATH:$GOPATH/bin"' >> ~/.bashrc
source ~/.bashrc
```

2. Verify that `go version` shows a go installation of version `>1.13.8`.

