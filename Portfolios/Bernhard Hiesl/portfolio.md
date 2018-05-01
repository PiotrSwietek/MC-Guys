# Portfolio for H&B Automation

## Introduction
I'm Bernhard I did the bachelor in mobile computing and the reason why i started studying is because i wanted to learn how to develop applications and all the stuff around it.

All tasks were done with the cooperation of [Denis](https://github.com/PiotrSwietek/MC-Guys/blob/master/Portfolios/Denis%20Sivak/portfolio.md).

### Expectations of class
I've already heard some stuff about home and building automation, for example making home automation application with an raspberry pi.
Or kinda google home or something like that. House control application with speech control.

### Pros
* Good ideas
* good design skills
* even if i'm not the best in programming i understand everything and can discuss hard problems

### Cons
* not really the motivation in person


## Videos

### The Big Bang Theory

#### Scenarios and application domains
* power control of different devices over the internet worldwide. some guys from all around the world control their devices
* SF - lissbon - and another city
* survey with the cars (privacy)

#### Technologies
* isp

#### Feasablitiy
1. What might be doable?
* yes nearly everthing expect the "public access"
2. What not?
Nothing here
3. When?
Nothing here

#### Weirdness/crazyness
Nothing here

### Siemens

#### Scenarios and application domains
* security entrance body scan
* automatic elevator with priority
* comfort?
* guide for other people
* light and speakers assist people in an emergency
* energy grids
* data evaluation

#### Technologies
* some unkown devices
* smart grids
* sensors

#### Feasablitiy
1. What might be doable?
	Nothing here
2. What not?
* holographic displays
* body/face recognition
3. When?
Nothing here

#### Weirdness/crazyness
* control center with holographic displays
* exchange offices

### Internet of Shrimps

#### Scenarios and application domains
* parody of devices nowadays

#### Technologies
* tablet
* micro controllers

#### Feasablitiy
1. What might be doable?
	Nothing here
2. What not?
Nothing here
3. When?
Nothing here

#### Weirdness/crazyness
* whole video was weird

## What is Home and Building automation
* Remonte control building environment
* Automating building environment using sensors (light, temp)
* monitoring
* energy efficencygit
* security (privacy)
* entertainment
* connect devices together
* convenience
* Transparancy

## 19.3.2018

### Setup the Raspberry Pi

First of all we flashed the prepared image on the raspberry pi. After the flashing we modified the config files (user, wifi,...) to connect later to the console of the pi via MobaXTerm.

### IoT Node
The second part of the lecture we went through the given tutorial with the topic IoT Node. Here we had to flash also a prepared image on the Wemos D1 Mini. After this process we were able to disconnect it from the pi, connect it again to another usb port and reconnect again via the pi by go into the node folder and execute the console command.

### Recap
*TODO*

## 22.3.2018

### Configure different nodes
In the second lecutre our task was to turn on/off a led with a button on another Wemos D1 Mini. To do this, we needed to flash another image on the Mini. On node1 we created a device "LED" and on the node2 we created a "BUTTON". With the run command the Mini publishes his events and with mqtt we configured paths (mqtt_action) so if the button got pressed on node2 the led on node1 gets toggled.

### Relay
Due to the speed of Denis and me we've allready finished the relay and lock tasks in this lecture. The relay was a simple "out" on D2 with the value on or off to lock and unlock the doorlock. Further task was to realise this via Node-Red

### Node-Red
The next task was to confiugre a simple lock/unlock button with Noder RED. If you click this butten the lock should be locked/unlocked. So Node RED provides us a UI. Node-Red just sends an MQTT message to the broker (Pi) which triggers the relay/lock.

### Recap
*TODO*

## 23.3.2018

### Control servo/lock vai a RFID-reader
* Created ad flashed new node
* Wired up the RFID
* Created a new device on the node
* Wrote data to a mifare classic card
* Ran the node run()
* Used Node-Red to check if RFID tag delivers the right code
* If the tag was right we unlocked the dor as long as the tag was hold on the RFID reader.

### Showing temp/humidity on LCD-display
* Created a new node for temp and humidity sensor
* Created a node for the LCD display
* Temp/humidity
	* Testing and showing values in a line chart via Node-Red
* LCD
	* Followed tutorial from ulnoiot to setup the display correctly
	* Tested the node via MQTT message displayed on the LCD
* Configured the MQTT actions via Node-Red to foreward the data

### Recap
*TODO*

## 3.4.2018
### OpenHAB
We downloaded and installed OpenHAB, but as we tried to start it as a service Windows refused this option. So everytime we want to use OpenHAB we have to start it manually.

### Debate
#### PRO
* More convenience
* Everything is smart and connected
* Growing industry
* energy efficiency
* fully automated tasks

#### CON
* less privacy
* another entrance for hackers
* complex

### Bus/Protocols
#### I2C
* I2C = Inter-Integrated Curcuit
* Designed by Philips
* Resent version = Version 6
* Serial and Half-duplex
* simple master/slave relationship
* multi-master bus arbitration and collision detection

* Speed: The clock is transmitted by the sender and the receiver is always able to synchronize with that clock. I2C defines several speed grades but * the term baud rate is quite unusual in this context.
* Throughput:  0.1 standrad mode / 0.4 full speed / 1.0 fast mode / 3.4 highspeed (depending on mode)   
* Length:  So the maximum bus length of an I2C link is about 1 meter at 100 Kbaud, or 10 meters at 10 Kbaud
* Usage example: micro controller, components connected via cable, control architectures such as System Management Bus (SMBus), Power
Management Bus (PMBus), Intelligent Platform Management Interface (IPMI), Display Data Channel (DDC) and Advanced Telecom Computing Architecture (ATCA).

#### Other

* RS232, RS442, RS485, DMX
* Onewire/X10
* Zwire/ZigBee
* KNX-bus/E-bus
* Modbus/CANbus
* BACnet

#### Favourite Bus/Protocols
* I2C
* SPI
* Zegbee

### Recap
*TODO*

## 10.4.2018

### KNX lecture
 To get more in touch with the KNX bus protocol we had to complete an online course at the following website: https://www.knx.org/knx-en/training/knx-eacademy/ets-ecampus/index.php

 After the completion of several questions and tasks I got an KNX certificate which could be found in my folder.

### MQTT Simulator
*TODO*

### IFTTT and Adafruit
*TODO*

### Philips Hue
The Philips Hue stuff was done by [Piotr](Portfolios/Piotr%20Swietek/portfolio.md), but I always checked the newest changes, because I was interested in the topic.

### Kodi
[Oliver](Portfolios/Oliver%20Barth/portfolio.md) was responsible for the Kodi part. This was not very interesting for me, because I've allready done this at home.

### Recap
*TODO*

## 17.4.2018

### Presentations Questions

Cheap devices but very expensive and timeconsuming planing?

Why only Loxone devices?

### Snowboy

* Created an account on Snowboy
* I've choosen one Hotword from the list: Jarvis, Zoe, Alexa.
* Recorded my voice 3 times saying the Hotword.
* After that a testing is needed to download the pmdl file from Snowboy.

To install and configure the microphone and Snowboy right on our Pi we had to use following commands and instruction:

* sudo apt-get install python-pyaudio python3-pyaudio sox

* pip install pyaudio

* some problems fixed with some other commands

	* virtualenv .p /usr/bin/python3 --system-site-packages .

	* . bin/activate

	* pip install pyaudio

* arecord to record temp.wav in bad and good quality

* arecord -f dat -D plughw:CARD=Device,DEV=0 temp.wav

* alsamixer

* sudo apt install libatlas-base-dev

* sudo apt install swig

* cd swig/Python3

* make

* wrong audiocards was used
 	* to fix this we had to add something in the asoundrc.
	* steps and code will be explained in the documentation of Snowboy

After this steps everything should be installed correctly and I could use the demo script and my pmdl file to test the hotword prediction of Snowboy.

## 19.4.2018

### Project 3 talk
We talkt about different scenarios which we want to implement for the Project 3. We decided to realise the scenarios we've allready described in the Project 2.

### RGB LED-Strip
In the last lecture I did the task with the led strip. Following steps will be needed:

* Flash a new node on the wemos d1 Mini
* create a rgb_multi device with the correct number of the LED's mounted on the strip
* connect the wemos d1 to a cable, because the usb cable probably will be to weak to power the wemos and d1
* run the run() function
* send MQTT messages to the wemos so the Strip will be turned on/off or changes its colors.

The cool thing about this led rgb_multi led strip is, that you can easily access every single led and independently change colors of it.

### Recap
*TODO*

## Problems & Lessons Learned
### SSH
I had some problems with the SSH connection to git. I cloned the github repository with the HTTP link not with the SSH link. After creating, adding and using the SSH stuff everything now is working. I've also helped my colleagues to setup this settings.

### Node Problem
The biggest problem this morning was, that we couldn't figure out which device is node 1 and node 2. Therefore we write it down

node1 = LED
node2 = BUTTON

### Servo
We didn't know how to configure the servo right. After the hint that we should use "servo_switch" it was easy to implement, because the servo_switch has a on/off function where it just switches to different given angles

### Snowboy
Nearly nothing was installed on the pi to use Snowboy instantly. look at the section Snowboy to see the command history.

## 26.4.2018

### Project Setup
[Denis](https://github.com/PiotrSwietek/MC-Guys/blob/master/Portfolios/Denis%20Sivak/portfolio.md), [Manuel](https://github.com/PiotrSwietek/MC-Guys/blob/master/Portfolios/Manuel%20M%C3%BChlschuster/portfolio.md) and I did nearly the whole node stuff. We flashed following nodes:
* Servo (Shutter, Windows,...)
* Button
* Multi RGB
* Lock
* Humiture Sensor

Another work package for me was the Node Red flows. I created some flows and also fixed and tweaked some errors of the other flows.

Last but not least I wos responsible for the voice control via the Google Assistent, IFTTT and Adafruit. We triggered an mqtt message by saying "Movie mode". So the IFTTT application sends the data to Adafruit and the MQTT broker listens via Node Red on the Adafruit changes/events.

### Project

# Fully Recap
