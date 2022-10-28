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

# M1 Mac work arounds (Credit Orchard)

1. edit ~/.zshrc with vim/nano. (if you are using a different shell you need to edit the corresponding config file, check which shell you are using https://github.com/UoB-CSA/setup-guides/blob/master/go-install/mac.md)

2. add followings (replace maxosx12.0 with your own mac os version)

```
export GOOS=darwin
export GOARCH=arm64
export CGO_CFLAGS="-isysroot $(xcrun --sdk macosx12.0 --show-sdk-path) -arch arm64 -I/usr/local/include"
export CGO_LDFLAGS="-isysroot $(xcrun --sdk macosx12.0 --show-sdk-path) -arch arm64 -L/usr/local/lib"
export CGO_ENABLED=1
```

3. go to your coursework folder and type go run .

Credit to [this source](https://github.com/veandco/go-sdl2/issues/479) about Go and SDL2 issues

# Mac fix for 2022-23
Get "Panic: Window Data not found"

Comment out error checking for w.window.Destroy() in Destroy method:
```
func (w *Window) Destroy() {
	err := w.texture.Destroy()
	util.Check(err)
	err = w.renderer.Destroy()
	util.Check(err)
	err = w.window.Destroy()
	//util.Check(err)
	sdl.Quit()
}
```
