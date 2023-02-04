# How To Make Your Own Artificial Spider Sense Device?

**Sincere apologies for any image copyright infringements! These blogs were created at the time I was unaware of the copyrights. If you want me to take down any image, feel free to reach out to me @ technopains@gmail.com. Keep the Subject as 'Image Copyright Issue' Thank you for understanding!**


We all have grown up watching cool superhero movies and cartoon series. Every superhero is involved either with some cool super power or super awesome sci-fi tech. Spiderman is one of those. I personally like the character most due to the fact I can relate so many things to him. The guy is so much like any youngster struggling with their everyday life and it feels good to see them on screen.

So today I'll explain to you the way to make your own Artificial spider sense device. For those of you who are unaware of what exactly is spider-sense. Well, it's actually kind of a sixth sense which aware Spiderman of dangers around him. It is shown more like a psychic power in TV series and cartoons but actually, it works in a different sense.

Spiders have very small and tiny hairs on their legs which are triggered due to air vibrations around them when something near them is moving or something creates any kind of disturbances they are able to catch those vibrations and then react accordingly. The same power is showed to be inherited by Spiderman when he gets a radioactive spider bite which mutates the spider DNA into his body altering its overall DNA replicating and hybridization takes places which ends up offering him spider powers like super strength, agility, speed etc.

Now let's discuss how we can create our own artificial based spider-sense. For this we will use:

## Arduino UNO

![Arduino UNO](https://cdn.wrytin.com/images/wrytup/r/1024/arduino-uno-r3-clone-with-usb-cable-usb-chip-ch340-21282-27-b-jw4d2j5j.jpeg)

## PIR Motion sensor

![PIR Motion Sensor](https://cdn.wrytin.com/images/wrytup/r/1024/pir-sensor-1000-grande-jw4chxvi.jpeg)

## Few Jumper Cables (Female to male)

![Jumper Cables](https://cdn.wrytin.com/images/wrytup/r/1024/816-fhwxcnl-sx425--jw4ciehu.jpeg)

## 5V Buzzer

![5V Buzzer](https://cdn.wrytin.com/images/wrytup/r/1024/sku125754a-jw4cjulf.jpeg)

## LED lights

![LED lights](https://cdn.wrytin.com/images/wrytup/r/1024/how-to-make-your-own-artificial-spider-sense-device--jw4cks53.jpeg)

## 9V Battery (For Power Supply)

![9V Battery](https://cdn.wrytin.com/images/wrytup/r/1024/bf22-9v-battery-3-jw4cldy6.jpeg)

##  Arduino USB cable

![Arduino USB cable](https://cdn.wrytin.com/images/wrytup/r/1024/how-to-make-your-own-artificial-spider-sense-device--jw4dm662.jpeg)

## Breadboard (small)

![Breadboard (small)](https://cdn.wrytin.com/images/wrytup/r/1024/64-00-jw4du4iv.jpeg)

This all will cost about 800 INR. You can use rough cardboard and Velcro strips to make mounts and make the device wearable.

Arduino UNO is basically a micro-controller which can be programmed to perform various tasks. A PIR sensor also known as passive infrared sensor is a device which extracts the infrared waves emitted and based on their instensity variation tracks the motion of the bodies which tend to emit infrared radiations like humans dogs etc. A fresnal lens is used to focus all the upcoming radiation and concentrate them to infrared sensetive area from which detection takes place.

![Passive Infrared Motion Sensor in Action](https://cdn.wrytin.com/images/wrytup/r/1024/how-to-make-your-own-artificial-spider-sense-device--jw4cozxs.jpeg)

Jumper cables are used to makehe physical connections between microcontroller sensor and other peripherals. An electronic buzzer, as the name suggests buzzes out sound under audible frequency and acts as alarm to threats, similarly an LED can perform the same job, giving optical based output instead of sound. A 9V battery can be used to operate all the sensor, LED and microcontroller. A USB cable is used to interface your microcontroller with your system and a breadboard helps in making physical connections in smoothly efficient manner.

Microcontroller programming is generally done in assembly languages, to program an Arduino UNO one should know embedded C, though if you don't that's not a problem as well as I have attached my own code, don't try to burn your head understanding this if you haven't programmed before.

```
int LED_OUTPUT=13;
int SENSOR=2;
int BUZZER=3;
void setup() {
    pinMode(LED_OUTPUT,OUTPUT); // initializing pinMOde 13 as output
    //this will help to trigger out the LED if motion is detected
    pinMode(SENSOR,INPUT); //2nd port from where we will recieve sensor data
    pinMode(BUZZER,OUTPUT); //to trigger the buzzer from 3rd port
    digitalWrite(LED_OUTPUT,LOW); //initially turning off LED
}
int trigger; // value to be digitally read by sensor either it's high or low
void loop() {
//infinite times running loop
trigger=digitalRead(SENSOR); //reading sensor data and checking if there's any motion or not
    if(trigger==HIGH) //if motion is present
    {
        digitalWrite(LED_OUTPUT,HIGH); //trigger led
        digitalWrite(BUZZER,HIGH); //trigger buzzer
        delay(500); //delay for 0.5 seconds
    }
}
```

I have tried to make the code as self-explanatory as it can be, still if you want to understand any part of it I'll be happy to assist.

Now once the coding is done, we need to make physical connections and upload the code to the micro-controller, there are many ways of doing so but the easiest will be to use the software Arduino IDE.

After uploading the code, use Arduino USB cable to connect the Arduino (microcontroller) with the PC, before this make the physical connections in the following manner:

## Pin configuration of Arduino:

![Pin Configuration of Arduino](https://www.electroschematics.com/wp-content/uploads/2013/01/Arduino-Uno-R3-Pinouts.png)

## Pin configuration of PIR sensor:
![Pin configuration of PIR sensor](https://cdn.wrytin.com/images/wrytup/r/1024/pir-sensor-pinout-jw4dq4zj.jpeg)

VCC port to 5V port of Arduino.
GND port to GND port of Arduino
Dout to Digital input pin 2 of Arduino.
There are some advanced options which you need not to consider as of now. Similarly, for LED you need to put larger end in Digital port number 13 and other ground it together using breadboard. For the buzzer, do the same procedure as that of sensor, only the Dout pin is supposed to be connected to digital pin 3 instead of 2. That's it, your artificial spider-sense is ready now, for now you don't need to connect anything with the battery as it is powered with your system, but for mobility purpose the setup needs to be powered using a 9V battery which is to be connected in 5V port of Arduino. Test the device and see your artificial spider-sense in action!

It may look something like this once its done:

![Arduino Connection to PIR Motion Sensor](https://cdn.wrytin.com/images/wrytup/r/1024/arduino-motion-detector-0-jw4e3mvk.jpeg)

Further microcontrollers are devices with so many peripherals and ports, their sizes can be reduced with application specific ICs also known as ASICs once you are done prototyping which comes under PCB designing and which is yet another vast topic to be covered here.