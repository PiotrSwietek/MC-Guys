# Portfolio for H&B Automation

## Introduction
I'm Bernhard I did the bachelor in mobile computing and the reason why i started studying is because i wanted to learn how to develop applications and all the stuff around it.

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

## 22.3.2018

### Configure different nodes
In the second lecutre our task was to turn on/off a led with a button on another Wemos D1 Mini. To do this, we needed to flash another image on the Mini. On node1 we created a device "LED" and on the node2 we created a "BUTTON". With the run command the Mini publishes his events and with mqtt we configured paths (mqtt_action) so if the button got pressed on node2 the led on node1 gets toggled.

### Node RED
The next task was to confiugre a simple lock/unlock button with Noder RED. If you click this butten the lock should be locked/unlocked. So Node RED provides us a UI.

## 23.3.2018

### Control servo/lock vai a RFID-reader
TODO!

### Showing temp/humidity on LCD-display
TODO!

## 4.4.2018
### OpenHAB

### Debate
#### PRO

#### CON

### Bus/Protocols

## 10.4.2018

## Problems & Lessons Learned
### SSH
I had some problems with the SSH connection to git. I cloned the github repository with the HTTP link not with the SSH link. After creating, adding and using the SSH stuff everything now is working. I've also helped my colleagues to setup this settings.

### Node Problem
The biggest problem this morning was, that we couldn't figure out which device is node 1 and node 2. Therefore we write it down

node1 = LED
node2 = BUTTON

### Servo
We didn't know how to configure the servo right. After the hint that we should use "servo_switch" it was easy to implement, because the servo_switch has a on/off function where it just switches to different given angles
