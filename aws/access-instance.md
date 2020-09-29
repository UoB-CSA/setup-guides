# Accessing an Instance

To access an instance you will need to use ssh. Linux and macOS support this in the terminal, or on Windows you can use WSL or Windows Terminal.

1. Locate the keypair that you downloaded from AWS when you started your instances.

2. Find the IP address of the isntance you would like to connect to. This will be shown if you click on a instance from the list you have created. In the example below the ip address is `52.90.29.156`

![ip address](content/ip-address.png)

3. Open a terminal.

4. Set your key to have the correct permissions by running `chmod 0600 keypair.pem` where `keypair.pem` is the path to the downloaded keypair

5. Use the command `ssh ubuntu@52.90.29.156 -i keypair.pem`. In this example replace the IP address with your IP and `keypair.pem` to the location of the keypair you downloaded.

You now have a terminal connected to the AWS instance.


## Coping files

The best way to transfer files between the two machines is to use a git repo for your work and clone the repo to the aws instance. To learn how to use git follow [this guide](https://www.ole.bris.ac.uk/bbcswebdav/users/csxdb/pub/git/index.html).


