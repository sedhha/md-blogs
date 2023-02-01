# Invisible Talking Camera Using Python

Hey fellas! I hope you all doing well, Here is something cool which I wanted to share with you guys. How many of you are Harry potter Fans? In case you’re, I hope you have seen that invisible cloak scene where Harry just goes invisible by using his cloak. Here’s the snapshot from the same:

![Harry Potter Invisible Cloak](https://media.giphy.com/media/J5lxA8X7kisRG/giphy.gif)

Now after watching this cool effect, I was just wondering if Can we produce the same effect using Computer Vision or Image processing and guess what? Of course we can.

If you carefully look into the image, you will observe the background is stationary, this is just an illusion to our eyes. According to my theory, there is a pre existing image which is already captured when there’s no Harry in the scene, finally the features of his cloak are been recorded in terms of colors and patterns. Once it is identified using the computer vision algorithms, the background image is being superimposed to those areas where there is cloak. Did you get it? Complex? huh! Okay let’s try it ourselves to understand this better.

So open your python console, you’ll need these libraries to make a realistic speaking invisible camera effect:

```
cv2
numpy
time
pyttsx3
```

(You can use any other text2speech library, but personally I like this cute female voice haha!)

Okay now let’s do this, first we need to capture a background image before beginning anything, you can write a python code for the same or just capture using windows camera and put it in your working python folder. Make sure nothing should come into the frame while capturing the image.

For this we can begin with:

```
import cv2
import numpy as np
import time
import pyttsx3
#importing the necessary libraries

#initializing the camera:

cam=cv2.VideoCapture(0) # laptop webcam in case you have something else use 1 2 #3 accordingly.

#Now if you want your laptop to talk to you use the command:

engine = pyttsx3.init()

message=’Type your message here.’

engine.say(message)

engine.runAndWait()
```

Now after executing this code, you should be able to hear your message. Once this one is done, let’s proceed to capture the calibration image (#i.e. our background) and this goes like this:

```
engine.say(“Clear out the background, I am going to capture image in 3s.”)

engine.runAndWait()

time.sleep(3)

_,calibrated=cam.read()

engine.say(“Check your calibrated image now.”)

engine.runAndWait()

cv2.imshow(“Calibrated Image”,calibrated)

hsv_L=(219,64,20)

hsv_U=(244,100,50)


```

Make sure that the range which you use, must fall under the range of color over which you are testing. You can obtain and check the binary image of the same by using the following piece of code: (All the white regions denote the part which are falling under that range)


```
_,frame=cam.read()

inRange_img=cv2.inRange(cv2.cvtColor(frame,cv2.COLOR_BGr2HSV),hsv_L,hsv_U)

cv2.imshow(“In range image”,inRange_img)
```

Once after checking that the image obtained is falling under desired range and you are getting exactly what you want proceed further.

Now everything is well defined, we need to just focus on filtering that region and super imposing it to the actual frames grabbed.

```
while True:
    k=cv2.waitKey(1)
    _,frame=cam.read()
    hsv=cv2.cvtColor(frame,cv2.COLOR_BGR2HSV)
    ranged=cv2.inRange(hsv,hsv_L,hsv_U)
    final=cv2.add(img,frame) #to create transparent effect
    final2=cv2.bitwise_not(img,frame,mask=ranged)
    imgf=np.concatenate([final2,final],axis=1)
    cv2.imshow(‘HarryPotter Invisible Cloak Effect’,imgf)
    if k & 0xFF==ord(‘q’):
        print(“Time to say goodbye! Take care.”)
        engine.say(“Time to say goodbye! Take care.”)
        engine.runAndWait()
        cam.release()
        cv2.destroyAllWindows()
        break
```

And that’s it we are good to go now. This code demonstrates superimposing using bitwise operations. Try using it in some other way (Hint: I have used bitwise not which actually superimposes not of one image to another, see if you can do with something else. 🙂 )


Here are my results:


![OpenCV Invisible Camera Cloak Harry Potter](https://technopain.files.wordpress.com/2019/05/capture.jpg)
![OpenCV Invisible Camera Cloak Harry Potter - 01](https://technopain.files.wordpress.com/2019/05/capture-1.jpg)
![OpenCV Invisible Camera Cloak Harry Potter - 02](https://technopain.files.wordpress.com/2019/05/capture-2.jpg)
![OpenCV Invisible Camera Cloak Harry Potter - 03](https://technopain.files.wordpress.com/2019/05/capture-3.jpg)

These are some of the effects, I created. Look at the background carefully, it’s slightly brown, Can you comment down the reasons for that?

Thanks 😀