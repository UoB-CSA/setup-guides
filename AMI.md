# Creating a clone instance

## Making an AMI 

We first want to make an image of our existing instance. This essentially takes the necessary information from the current state of the instance and saves it as a AMI (Amazon Machine Image). When doing this, make sure that the instance's state is running, rather than pending.

<img src="Capture1.PNG" alt="drawing" width="640"/>

Then fill in the name for the image:

<img src="Capture2.PNG" alt="drawing" width="640"/>

And click create image:

<img src="Capture3.PNG" alt="drawing" width="640"/>

You've now made your image! To find it, just head to the AMI section in the dashboard:
 
<img src="Capture4.PNG" alt="drawing" width="150"/>

## Using your AMI 

Now that you have your image, you're going to want to make it useful. Head to the AMI page, and select the one you want to use. Then hit the "lauch instance from AMI" button:

<img src="Capture5.PNG" alt="drawing" width="640"/>

Fill in the name of your new instance:

<img src="Capture6.PNG" alt="drawing" width="640"/>

Make sure that your image is being used:

<img src="Capture7.PNG" alt="drawing" width="640"/>

Hit the launch instance button, and you're ready to go!