# Setup instructions for macOS

These instructions were prepared on the following hardware:
* Intel Mac running Ventura 13.5.1
* M1 Mac running Ventura 13.5.2
## **If you do not have clang, sdl2, gcc etc. (xcode) [then please complete this guide first](mac_prelim.md)**

# Go installation 
1. For Apple Silicon (M1/M2), download version **go1.17.13** of Go and for Intel Silicon (AMD64/x86-64) download version **go1.18.10**

   > **NOTICE:**
   > **Please make sure you know whether you are using an Apple Silicon (M1/M2) Mac or an Intel Mac, google if you don't know.** 
   > * If you are an **Apple Silicon Mac**, download `Apple macOS (ARM64)`, typically named `go1.xx.x-darwin-arm64.pkg` [HERE](https://go.dev/dl/go1.23.1.darwin-arm64.pkg)
   > * If you are an **Intel Mac**, download `Apple macOS(x86-64)`, typically named `gox1.xx.x-darwin-amd64.pkg` **(amd64 here instead of arm64)** [HERE](https://go.dev/dl/go1.23.1.darwin-amd64.pkg)

2. Run and follow the prompts to install Golang.

3. Edit `~/.zshrc` by typing `open ~/.zshrc` in terminal (or use vim/vscode if you like), add the following lines to the bottom of the file:

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

4. Save the file and exit.

5. Close and re-open any terminal windows.

6. Verify your installation with the command `go version`. The version needs to be **higher** than **1.13**.

# Mac fix for 23-24 (If you get the error: cgo: malformed DWARF TagVariable entry) 

Upgrade to latest Go version - **you must limit yourself to language features in 1.17 and before**
```
sudo rm -rf /usr/local/go
sudo rm /etc/paths.d/go
brew install go
```
Credit Phillip Daniel

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

