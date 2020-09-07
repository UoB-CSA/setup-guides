# Personal Linux setup instructions

## Setup instructions for Ubuntu 20.04 LTS (focal)

1. Run the following commands in terminal. If bash is not your default shell, subsitute `.bashrc` for the appropriate file (e.g. `.zshrc` for zsh).

```bash
sudo apt-get update
sudo apt-get install golang=2:1.13~1ubuntu2 --yes
echo 'export GOPATH="$HOME/go"' >> ~/.bashrc
echo 'export PATH="$PATH:$GOPATH/bin"' >> ~/.bashrc
```

2. Verify that `go version` shows a go installation of version `>=1.13`.


## Setup instructions for Arch Linux

1. Run the following commands in terminal. If bash is not your default shell, subsitute `.bashrc` for the appropriate file (e.g. `.zshrc` for zsh).

```bash
sudo pacman -S go
echo 'export GOPATH="$HOME/go"' >> ~/.bashrc
echo 'export PATH="$PATH:$GOPATH/bin"' >> ~/.bashrc
```

2. Verify that `go version` shows a go installation of version `>=1.13`.

## Setup instructions for other Linux installations

1. Run the following commands in terminal:

```bash
wget https://dl.google.com/go/go1.15.1.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.15.1.linux-amd64.tar.gz
```

2. Open your `.bashrc` file (`~/.bashrc`) in your editor of choice. Add the following lines to the bottom of the file:

```bash
export GOPATH="$HOME/go"
export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"
```

3. Save the file and exit.

4. Close and re-open any terminal windows.

5. Verify your installation with the command `go version`. The version **will be `1.15.1`**.
