# AWS setup instructions


## Setup instructions for AWS Amazon Linux

For Amazon Linux 2, the default login username is ec2-user

1. Run the following commands in terminal to install Go and sdl2 (normally this is not needed as it's in headless environment):

```bash
sudo yum install go
echo 'export GOPATH="$HOME/go"' >> ~/.bashrc
echo 'export PATH="$PATH:/usr/local/go/bin:$GOPATH/bin"' >> ~/.bashrc
source ~/.bashrc
```

2. Verify your installation with the command `go version`. 
