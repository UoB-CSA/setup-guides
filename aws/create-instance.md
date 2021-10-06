# Creating an AWS Instance 

This will help you setup an instance on AWS.

* Log into Amazon Academy using the email you were sent and click "AWS Academy Learner Lab - Foun..." (magenta box in image):

<img src="content/aws1.png" alt="drawing" width="640"/>

* Click "Modules" (drawn around by hand):

<img src="content/aws2.png" alt="drawing" width="640"/>

* Click "Learner Lab - Foundational Services"

<img src="content/aws3.png" alt="drawing" width="640"/>

* Click "Start Lab"

<img src="content/aws4.png" alt="drawing" width="640"/>

* Click the (now green not red) AWS link (drawn around by hand):

<img src="content/aws5.png" alt="drawing" width="640"/>

* Click Launch a virtual machine With EC2 (drawn around by hand):

<img src="content/aws6.png" alt="drawing" width="640"/>

* Select Amazon Linux 2 AMI (HVM):

<img src="content/aws7.png" alt="drawing" width="640"/>

* You now need to select an instance type. If you are working on labsheets or just testing your coursework, use a t2.micro instance. If you are benchmarking your distributed system use a c4.xlarge instance. Once you have chosen the instance select "next".

* Most settings on this page **do not** need to be changed, the only one you should worry about is the number of instances to start. Once this has been set, select "next".

![Number of instances](content/number-instances.png)

* Select "next" on the storage section. You do not need to change any settings here.

* Add a tag, choose something that will help you identify the instance in the future, for example a lab name.

![Tags](content/tag.png)

* Leave the security group settings as default and select "review and launch".

* Now click "launch". This will open a popup box to set the keypair. If you have already got a keypair setup select it, **make sure you have the key downloaded somewhere**. If you cannot find the pre-existing key or do not already have one setup, create one and download it. **Make sure you keep it safe. If you lose it you will not be able to access your instances.**

* Now click "launch instances". This will start your instances.

* Follow the [next guide](access-instance.md) to get access to your instance.

* Once you have access you will need to install Go by following option 1 in [this guide](../go-install/aws.md).
