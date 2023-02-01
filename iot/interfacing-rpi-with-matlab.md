# Interfacing Matlab With Raspberry Pi


Hey everyone! After so long time I am posting this new blog about interfacing your Raspberry Pi with Matlab, sounds cool right? Now you can use your command window to do so much into your raspberry pi, so let’s begin.

Raspberry Pi is a pretty common microprocessor and almost used in many robotics, IOT, mobility projects etc. If you are a robotic enthusiast like me, I am sure you must be aware of microcontrollers and microprocessors, they make the overall life easier and better, they are lightweight, cheap and provide us with so many functionalities.

In the world of Linux and Python, which is an open source platform to develop such projects, people rarely want to explore a premium paid software like MATLAB. And in fact, if you are also an open source developer, or if you don’t have a proper licensed MATLAB, it’s better to go with Linux and python. But this article is all about exploring the limits and using MATLAB to program your Pi and control it wirelessly using MATLAB command window. So let’s start with setting things up.

 

Before you begin, make sure you have hardware package for raspberry pi installed as an add-on in your MATLAB, that’s something really necessary. Here you can see the [details](https://in.mathworks.com/matlabcentral/fileexchange/45145-matlab-support-package-for-raspberry-pi-hardware).

Also, I have noticed that normal Raspbian OS doesn’t work good with MATLAB, and to my best knowledge, it always shows some issue while accessing it, so the Mathworks team has come up with their own version of raspbian OS, which works really well with MATLAB, you need to download this OS from [here](https://github.com/mathworks/Raspbian_OS_Setup/releases/download/R18.1.0/mathworks_raspbian_R18.1.0.zip), or during the installation setup also you can get the link to download the OS, so that’s not an issue. You need to have one fresh SD card to upload the OS which you downloaded previously, in order to write it to your SD card.

Once you are done with that and ready with your SD card, put it in your SD card reader and open your MATLAB and type targetupdater in command window as shown below:

```
>> targetupdater
```

The following window is most likely to pop out:

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/1111.jpg)

Now if you have already installed the hardware support package, you will get a pop-down menu as Raspberry Pi, In case you haven’t, you can’t proceed next to this. So ensure that you have done it. Now click on the next button to proceed with your setup. Once you click next, here’s the window which pops out to further continue your installation:


![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/21.jpg)

Here you need to carefully select your board. In case you’re having trouble identifying your board, you can drop down in the comments, the most recent ones are the raspberry pi model 3b and model 3b+. You can differentiate between the two by looking at their BCM2837 chipset cover which is made up of aluminum in case of 3b+ and general plastic material in case of 3b. Aluminum was used most probably for better heat transfer, as these kinds of processor heat up really quick. On the other hand, old models of raspberry pi have BCM2835 chipset with 700 MHz frequency, the newer ones have 1.2GHZ (3b) and 1.4GHZ (3b+) respectively. Plus the older models and 3b can be differentiated by looking at the icon of raspberry pi which is quite bigger in case of older models, Haha… at least that’s something, I noticed. Anyways the older ones like raspberry pi 1 are completely different with a yellow colored audio jack, in addition to which we also have only 2 USB ports as compared to newer Pis. And Raspberry pi 0 stands completely different to all this and you can easily figure it out just by looking at it’s shape and size.


![Raspberry Pi 3B Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/3b.jpg)

Raspberry Pi 3B

![Raspberry Pi 3B+ Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/14643-Raspberry_Pi_3_B_-05.jpg)

Raspberry Pi 3B+


So once you’re done with selecting the Pi. Click next and follow the steps as shown in figure.

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/111.jpg)

You can customize and install more features to your existing operating system by going with the second option but that’s actually not required, as this is your first-time :D. Though, I would advise you to try it once you are done with your first installation as well.

Also, a proper detailing about all this is given in extreme right of the setup window, have a look at it while proceeding, they are really helpful to understand and set up your pi.

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/111-1.jpg)

As I told you, you will see this window to download your Matlab version of the raspbian OS, In case you have already downloaded go to next or else you can click on download hyperlink, to begin with downloading.

In the next window, you need to validate your downloaded zip file and browse to the path and validate it. If you have downloaded the right file properly, it will appear like this:

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/111-2.jpg)

Else it may show invalid. In that case, you may try downloading it again or restart your entire setup. Once this step is done again click next.

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/22.jpg)

Now, this step is really important, for setting up your Raspberry Pi. I will suggest going with option 2, i.e. connect to a wireless network. Since once it is set, you can setup a wired connection very easily. Depending upon your requirements you may follow any one of these. But again, if you want to use your Raspberry pi wirelessly, the second option is the best. Here I’ll explain the second option, you may go with first or others depending on your requirements, I can help you with the basics of the first option as well. For that, you must connect your pi to your PC, with an ethernet cable. In case you have questions for any other options, leave them in the comments below.  Now once you proceed with option 2, let’s navigate through the next steps.

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/21-1.jpg)

Here, it’s healthier to give automatic IP assignment, as if first 3 segments go for mismatch then it can cause an issue. Now switch on your mobile hotspot and enter the details, like SSID and password in the given columns. Also, try to have an SSID with no spaces as it makes the job easier for the OS to connect to it without getting confused. You can change your SSID as well with your phone and can give a one word convenient SSID.

Once these parameters are set, hit next. Mount your SD card into the card reader and insert it in your laptop, identify your SD card drive name here and hit next and wait for some time.

![Raspberry Pi Loading with Matlab based Raspbian OS](https://technopain.files.wordpress.com/2018/12/21-2.jpg)

Now the process begins, make sure your SD card is inserted in the entire process. Once the OS is being mounted into the card, eject the card and plug it into your raspberry pi. Before detecting your pi, make sure your hotspot is switched on, so that pi can connect to it. Power the pi via USB cable, and allow it to connect to your hotspot which was provided in the earlier step. Now once it succeeds you can proceed easily through the next steps which will navigate you to connect to your pi. The IP Address will be displayed on the screen and in case you forget it, one good feature of raspbian is that if you connect your headset to the pi’s audio jack, while you power it on, you can hear a voice which speaks out the IP address of the Pi.

Now all the setup is done and you are ready to use your pi.  Let me know if you still face any issues in the comments.

Cheers!


