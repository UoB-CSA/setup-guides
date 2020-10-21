# AWS setup instructions


## Setup instructions for AWS Ubuntu 20.04 LTS (focal)


1. Run the following commands in terminal:

```bash
wget https://dl.google.com/go/go1.15.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.15.3.linux-amd64.tar.gz
echo 'export GOPATH="$HOME/go"' >> ~/.bashrc
echo 'export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"' >> ~/.bashrc
source ~/.bashrc
```

5. Verify your installation with the command `go version`. The version **will be `1.15.3`**.
