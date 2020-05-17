# Setup instructions for Linux

2. Run the following commands in terminal

```
wget https://dl.google.com/go/go1.14.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.14.3.linux-amd64.tar.gz
```

3. Open your `.bashrc` file using `gedit ~/.bashrc` in terminal. Add the following lines to the bottom of the file.

```
export GOPATH="$HOME/go"
export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"
```

4. Save the file and exit.

5. Close and open any terminal windows.

6. Verify your installation with the command `go version`. The version should be 1.14.3
