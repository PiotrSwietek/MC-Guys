# Introduction

My name is Piotr Swietek and I am studying Mobile Computing and I also did my Bachelors degree here in Hagenberg. I am studying mobile computing because I like developing for mobile devices.

I take this class because I am interested in this topic and would like to have an introduction to this field. And maybe I will automate my own home in the future.

I am probably more the programming type in a group. I can realize the ideas of others in form of code.

# Filmnotes

## Big bang theory
### Scenarios and domains
	turn lamp online
	turn stereo on
	remote cars
	public access

### Technologies
	laptop
	internet

### Feasable?
	yes doable
	
### weirdness
	the steering through internet is not crazy
	but public access is
	
## Smart buildings - Siemens

### Scenarios
	security
	flexibility
	efficiency
	comfort & health
	personal navigation
	lightning used for navigation

### Technologies
	standard interfaces
	plug and go

### Feasable
	yes could be doable but requires a lot of ressources to do

### weirdness
	not really
	
## Internet of Shrimps

### Scenarios
	use IoT for controlling kitchen tools
	own soda dispenser in the phone

### Technologies
	heavy modified smart phone

### Feasable
	not really - because why?

### weirdness
	very weird
	
# Setting up Raspberry Pi

I downloaded the image from ulnoiot and made sure that the checksum is the same as stated on the source site.
Then I flashed the SD card with it using Etcher.
[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#raspberry)

When entering the SD I thought the Pi is broken because I did not felt the spring when I inserted the card but the proffessor told us this Pi has no spring installed so all was fine.

Then I started the Pi and connected to it via the ssh agent (MobaXTerm).

After the raspberry was set up correctly and I can log into the created WiFi mc_guys2

In this exercise I learned how to set up a raspberry pi with a flashed SD card and how to configure it.

# IoT domains

Healthcare - Monitor hand hygiene compliance through IOT device and sensors to reduce transmission of Hospital Acquired Infections to patients.  
Transport and logistics - Monitoring the logistics vehicles health to send alerts.  
Retail - Remote interaction with products increase personalized shopping experience.  
Insurance - Tracking clients' activity and offer discounts or rewards for healthy and safe behavior.  
Farming - Tracking soil health and climate.  

## Devices:
* smart locks
* smart plugs
* smart lighting
* smart thermostats

# Node onboard_blinker

I set up an LED which can be controlled with MQTT through an internet connection.
[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#iot-nodes)

At first I was a bit overwhelmed but after spending some time reading the ulnoiot documentation things got clearer and I could complete this exercise.

In this exercise I learned how to use the ESP8266. I have never worked with it before and it is remarkable how much you can do with such a small device.
Also I used MQTT the first time and I like it so far. I think it is quite easy to set up controllable light source. The same steps could be used to control lights
in my own home. This would not be too much work either which is impressive.

# H&B Automation Term - what is it used for

* Make life easier / convenience
* Security
* Energy efficiency
* Lighting
* Heating
* Indoor positioning
* Safety (fire & waterdamage)

# MQTT - NodeRed

Task was to steer the blinker through a button. But both were on seperate devices only communicating through the WiFi.
I followed the solution of Bernhard Hiesl & Denis Sivak [Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#ulnoiot-hello-world)

The MQTT commands caused us trouble because I forgot that I had to use them on the pi and not in the device console.
Also I forgot to execute the run() command so all the MQTT set requests would not be executed.

I also edited the autostart.py file of the devices so I didnt had to define the devices every time I connected it to the power.
First I always flashed the device when editing the autostart.py to copy it onto the device but then I realised I could use the deploy command to copy it.

In this exercise I learned what NodeRed is and it looks like a very nice and convenient tool to define network processes. Also it was fascinating when it all worked.
I had some trouble setting it all up but in retrospective it isnt hard at all.

# Smart Lock

Task was to control a magnetic lock through a graphical UI in the web using NodeRed. [Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#control-servolock-vai-a-rfid-reader)

The lock would be steered through a relay(electrical switch). I connected one connector of the lock to the power supply and the other to the relay.
The relay was connected to the powersupply of the lock and the lock itself. Now I have to define a new device for the output port:
d("out","output",d2);

Now when I run the command output.evaluate() and the lock locks/unlocks which is pretty awesome.

I had problems finding out how to set up the wiring correctly but in the end it worked nicely. But I may have used a wrong power supply for the lock because it became VERY hot.
It even started to smell burned so I disabled the power of it. I tried to connect it with a weaker power supply but then the magnetic lock did not work properly because it was too weak.

# Temperature and Humidity + LCD

Task was to set up a temperature and humidity sensor which is connected to the LCD display. The LCD should show the temperature and humidity in real time. [Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#showing-temphumidity-on-lcd-display)

The temperature setup was no problem at all. Because it was the same procedure with all other nodes. The LCD on the other hand did create some problems.
First I connected the LCD wrong with the controller so I did not work at all. But after reading the documentation it worked properly.
The next problem was to create a script in NodeRed which deletes all existing text on the LCD and prints the temperature and humidity. After some time I managed to 
write this script.

# Homeassistant install

First install python 3
execute pip3 install homeassistant
execute py -m homeassistant --open-ui --> but error came up
navigate to folder %APPDATA%/.homeassistant
execute hass command
open browser and navigate to localhost:8123
homeassistant UI is opened

I had problems installing Homeassistant on my Windows PC. The Installation guide for windows was a little bit hidden but I managed to find it. After I installed Python I tried
to execute the commands stated in the guide but it took more than a hour to execute this command so I interrupted it.

# Debate
I was in the Contra team but I was in the audience so I took notes:

## PRO
### Phase 1  
automated home examples, smart light, smart heating, energy consumption.
Comparison smart home - normal human -> more happy, more comfortable
happyness through convenience
easy to install
easy to upgrade
______________________________________________________
Home automation is growing, a lot of customization
market is becoming more open and accessible
other devices have cameras too but not much security breaches there

### Phase 2
Eldery people:
Elderly people can learn simple functionality like switching light on/off

Security:
Dont put cameras where you dont want them
Turn on camera wiith key words
Hackers are not interested
Change password dont use default settings




## CON
### Phase 1  
hacked locks/camera, less security against thieves
loss of privacy
______________________________________________________
too complex for older people
costs are high
experts are very expensive for installing home-automation systems

### Phase 2
Elderly people:
Elderly people dont use smartphones they use phones with big buttons
they like old stuff

Security:
Smart TVs record audio in living room and send to third parties
Data is important and collection of it is very profitable



## Questions:
What is the security difference between normal locks and smart locks? Both can be cracked open/hacked?
Same security problems with smartphone cameras but its different to see into the home vs into the inside of a pocket.
How do you think homeautomation can help developing countries?

# Bus presentatinos

## zigbee
for low power low bandwidth needs
small scale projects
simpler and cheaper
not suitable for movable devices

## zwave
nodes can talk to each other
low latency and reliable
les energy than wifi but higher signalrange than bluetooth

## SPI
full duplex
with shared clock

## I2C
clock transmitted by sender
serveral speed grades (from 0.1 mbits to 3.4 mbits)

## Onewire
device communication bus system
multiple slaves on 2 wires
distance 300m

## x10
communication among electronc devices
3kbits
cheap available
latency = 100 ms
low reliability
powerline device

## knx
succesor of EHS BartiBus
9.6 kbits
length 1km
supports different bus topologies

## ebus
2wire serial bus100m
2400baud
used in heating and solar appliances

## canbus
used in vehicles
used to replace copper
1mbit @ 40m
50kbits @ 1km
multi master

## Mobus
own PLC
standard for industrail electronic deviceseasy to deploy
master/slave with unique adresses

chosen: SPI, I2C, zigbee

# KNX Course

In this class whe had to go through the KNX course and do the test to get the [KNX certificate](https://github.com/PiotrSwietek/MC-Guys/blob/master/Portfolios/Piotr%20Swietek/knxcertification.pdf).

# Phillips Hue

In this exercise we had to set up a Phillips Hue Lamp and controll it through MQTT commands or NodeRED. [Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#philips-hue-lamps)

I had a lot of trouble setting up the Phillips bridge but after some time we managed to get it working. The Problem was that the bridge hat no internet access. I figured out how to set it up correctly: I had to connect everything before the pi did bootup and then it worked.

Setting up nodered to control the HUE Lamp was quite easy. In the end I could controll the brightness and Color of the lamp and I could turn it off remotely.

Out of all exercises I liked this the most. It was really fascinating seeing the lamp go on when you press a button in the web UI. I also liked it because it was like automating your own lighting in the real world. The lamps may be expensive but I think they are worth it.

# Distance sensor/Motion Detector

The task was to set up a distance sencor to function like a motion sensor. [Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#distance-sensormotion-detector)

I lost almos 2 hours setting up the distance sensor becaus it just would not work... Then I realised that the sensor was defect and my approach worked with another sensor perfectly. This has upset me alot because I did everything correctly but the sensor wouldn work.

When I set the sensor up I could get the measured distance through MQTT. I wrote a function to detect movement in NodeRed.

I think that the distance sensor is not a reliable motion detector but it could kind of work indoors I guess. Sadly we had no real motion detectors available.

# [Project 2](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project2)
The project was about automating a friends house. We have written a [scenario](https://github.com/PiotrSwietek/MC-Guys/blob/master/Projects/project2/Automate-your-friends-home_scenario.pdf) for the family which lives in the house we want to automate.

Our team nearly missed the deadline but in the end we managed to deliver a good plan and list of parts we needed.
We also got a lot of praise on our scenario which was quite surprising to me because we did not really put a lot of effort into it.

Thankfully the presentaion went smoothly and with no problems.

Some notes and questions from the other presentations:

Internationals

* Rich luxurious people who want the best. (paul and rachel)
* Some crazy ideas like outfit system in the walk-in closet
* very detailed workload plan 

Different devices from different manufacturers? Is it all possible to connect? Is it a lot of work?

ENI

* A smart and wealthy but paranoid guy
* Has a dog (but sadly only mentioned in scenario)
* Presentation itself very technical and almost too long

Why did you choose loxone? Is it possible to mix loxone parts with other?

# [Project 3](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project3)

Project 3 was about defining some scenarios and implementing them ourselves.

We used our written scenario from Project 2 and picked out some more interesting ones to recreate.

I was responsible for the HUE Lamps and the whole security apsect (motion detector/lock/rfid/alarm sound).

The presentation was a bit wonky because we have built everything live and one member of our team connected the nodes as the presentation went on. For a live presentation it went really well actually.

Notes on other presentation:

ENI:
* cool selfmade water boilder
* good presentation 

Internationals:
* unfortunatly no live demos but videos were nice too
* a bit disconnected from their actual scenario

# Reflection

All in all the course was very different from the other courses. Most of the classes we spent tinkering around with devices which was really nice. I also liked the amount of sensors and devices we had at our disposal. We did not really learn a lot whats going on behind the scene though. We kind of just used some commands from the UlnoIOT framework (which I dont know what it is exactly) and used some high level MQTT commands and eveything worked. I wish we would get a little background information what UlnoIOT really is, what is it architecture and so on. I did not like the fact that we used the Matrix chat and that the course utilities were not on the standard moodle elearning platform the students are used to. It was sometimes really confusing when some informations regarding the project deadlines or content were changed from the slides and only mentioned in the matrix chat. I was not online in the chat everyday and it happened that I overlooked some vital informations which was frustrating.

In summary I liked the course a lot. We learned a lot of useful things and the course gave me a kickstart in the homebuilding field, which was my hope for this course.


