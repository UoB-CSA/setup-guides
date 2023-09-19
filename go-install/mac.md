# Setup instructions for macOS

1. Get **macOS** ready for the Go install by running `xcode-select --install` in terminal. Follow the onscreen prompts to install.

2. Download version go1.17.13 of Go for **macOS** from [here](https://golang.org/dl/).

   > **NOTICE:**
   > **Please make sure you know whether you are using an Apple Silicon (M1/M2) Mac or an Intel Mac, google if you don't know.** 
   > * If you are an **Apple Silicon Mac**, download `Apple macOS (ARM64)`, typically named `go1.xx.x-darwin-arm64.pkg` [HERE](https://go.dev/dl/go1.17.13.darwin-arm64.pkg)
   > * If you are an **Intel Mac**, download `Apple macOS(x86-64)`, typically named `gox1.xx.x-darwin-amd64.pkg` **(amd64 here instead of arm64)**

3. Run and follow the prompts to install Golang.

4. Edit `~/.zshrc` by typing `open ~/.zshrc` in terminal (or use vim/vscode if you like), add the following lines to the bottom of the file:

   ``` bash
   export GOPATH="$HOME/go"
   export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"
   ```
   > **NOTICE:** If your terminal says `The file /Users/your_username/.zshrc does not exist`, you need to type `touch ~/.zshrc` to create the file first.
   > `~` is your user directory, typically equals to `/Users/your_username/`.
 
   > **NOTICE for old mac:** Apple has now switched from **bash** to **Zshell** and if you are using a very old version of macOS you may need to type `echo $SHELL` in terminal to check which shell you are using.
   > 
   > If it says `/bin/zsh`, then you are using **Zshell** and everything is fine.
   > 
   > If it says `/bin/bash`, then you are using **bash**, you can type `chsh -s /bin/zsh` in terminal to set Zshell as your default, or continue with bash and writing those two lines to `~/.bash_profile`.

5. Save the file and exit.

6. Close and re-open any terminal windows.

7. Verify your installation with the command `go version`. The version needs to be **higher** than **1.13**.

# M1 Mac work arounds (deprecated)

> **NOTICE: This has been deprecated and will be removed next year.**
> 
> This workaround was for CGO and no longer worked on the latest macOS 13 Ventura.
> 
> It is deprecated and not needed, don't follow this anymore.
> 
> If you followed this workaround before and started to see `2022-xx-xx xx:xx:xx.xx xcodebuild[4356:201382] Writing error result bundle to /xxxxx.xcresult
xcodebuild: error: SDK "macosx13.0" cannot be located.` at every startup in terminal, please remove (reverse doing) these from your `~/.zshrc`

Remove ~~Add following lines to `~/.zshrc`~~ 

``` bash
export GOOS=darwin
export GOARCH=arm64
export CGO_CFLAGS="-isysroot $(xcrun --sdk macosx$(sw_vers -ProductVersion) --show-sdk-path) -arch arm64 -I/usr/local/include"
export CGO_LDFLAGS="-isysroot $(xcrun --sdk macosx$(sw_vers -ProductVersion) --show-sdk-path) -arch arm64 -L/usr/local/lib"
export CGO_ENABLED=1
```

# Mac fix for 2022-23
## pkg-config error
In your terminal run: 

```brew install sdl2{,_image,_mixer,_ttf,_gfx} pkg-config```

## Window data panic
Get "Panic: Window Data not found"

Comment out error checking for w.window.Destroy() in Destroy method:

``` golang
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

