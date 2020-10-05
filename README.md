# Setup Guides

## Installing Go
To help you get started here are some setup guides for Go:

- [Linux Lab Machines](go-install/lab-machines.md)
- [Personal Linux PCs](go-install/linux.md)
- [MacOS](go-install/mac.md)
- [Windows](go-install/windows.md)

## Working From China

Commands such as `go get` will not work since `proxy.golang.org` is currently blocked in China. You can fix this by running the following commands to set up a Go module proxy:

```
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```

## Editors

There are also some setup guides for popular IDEs:

- [VSCode](editors/vscode.md)

## Using AWS

You should have received an email from AWS Educate to setup your account. Complete the application to get access to your account and $50 of credit.

**It is important that you look after this credit! Once it's gone it's gone! Don't run instances when you aren't using them.**

We advise that while you are testing your implementation you use a t2.micro instance. When you want to run benchmarks on your Game of Life coursework you should use a c4.xlarge instance. **Do not just use a c4.xlarge for regular development and testing, you will likely run out of credit if you do!**

These are some guides that we have created to help you setup your AWS instances.

- [Creating an instance](aws/create-instance.md)
- [Accessing an instance](aws/access-instance.md)
- [Opening ports](aws/ports.md)

## Detailed set up guides with videos

- Install Go on Ubuntu via Snap [video](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallGoOnUbuntuViaSnap/Install_Go_on_Linux_via_Snap.mp4),[transcript](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallGoOnUbuntuViaSnap/snap.htm)
- Install Go on Linux Via a Binary Release [video](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallGoOnLinuxViaABinary%20Release/Install_Go_on_Linux_via_a_binaryRelease.mp4), [transcript](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallGoOnLinuxViaABinary%20Release/binary.htm)
- Install and Configure IntelliJ Ultimate [video](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallAndConfigureIntelliJUltimate2019.2/InstallandconfigureIntelliJUltimate%202019.2.mp4),[transcript](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/InstallAndConfigureIntelliJUltimate2019.2/intellij.htm)

## Debugging Help

- Tracing in Go [video](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/TracingInGo/HowToMakeAtraceOfMultipleThreads.mp4),[transcript](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/TracingInGo/tracing.htm)
- Debugging with Delve [video](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/DebuggingWithDelve/debugging_with_delve_1.mp4),[transcript](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS20008_2020_TB-1/CONTENT_2020/tuts/DebuggingWithDelve/delve.htm)

