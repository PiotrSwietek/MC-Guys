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
//Link protocol

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
//Link protocol

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
I followed the solution of Bernhard Hiesl & Denis Sivak //Link here

The MQTT commands caused us trouble because I forgot that I had to use them on the pi and not in the device console.
Also I forgot to execute the run() command so all the MQTT set requests would not be executed.

I also edited the autostart.py file of the devices so I didnt had to define the devices every time I connected it to the power.
First I always flashed the device when editing the autostart.py to copy it onto the device but then I realised I could use the deploy command to copy it.

In this exercise I learned what NodeRed is and it looks like a very nice and convenient tool to define network processes. Also it was fascinating when it all worked.
I had some trouble setting it all up but in retrospective it isnt hard at all.

# Smart Lock

Task was to control a magnetic lock through a graphical UI in the web using NodeRed.

The lock would be steered through a relay(electrical switch). I connected one connector of the lock to the power supply and the other to the relay.
The relay was connected to the powersupply of the lock and the lock itself. Now I have to define a new device for the output port:
d("out","output",d2);

Now when I run the command output.evaluate() and the lock locks/unlocks which is pretty awesome.

I had problems finding out how to set up the wiring correctly but in the end it worked nicely. But I may have used a wrong power supply for the lock because it became VERY hot.
It even started to smell burned so I disabled the power of it. I tried to connect it with a weaker power supply but then the magnetic lock did not work properly because it was too weak.

# Temperature and Humidity + LCD

Task was to set up a temperature and humidity sensor which is connected to the LCD display. The LCD should show the temperature and humidity in real time.

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

## PRO
### Phase 1
automated home examples, smart light, smart heating, energy consumption.
Comparison smart home - normal human -> more happy, more comfortable
happyness through convenience
easy to install
easy to upgrade
=======================================================================
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
======================================================================
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