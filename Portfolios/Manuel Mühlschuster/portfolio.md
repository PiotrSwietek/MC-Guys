# Portfolio for H&B Automation

## Introduction

My name is Manuel Mühlschuster and I am studying Mobile Computing, because I like to learn about new technologies in mobile devices and to write awesome smartphone applications.

### Pros

Good programming skills.
Good communication skills.

### Cons

Not a good knowledge of Hardware.

## Summaries of the shown videos

### Video 1: Big Bang Theory Snippet

Scenarios and application domains:
* Control Lights, Stereo, RC vehicles
* (Public) Access over internet

Technologies:
* Internet

Feasibility:
What might be doable?:
* Controlling electronic devices over the internet

What not?
* Everything shown is possible up to date.

Weirdness/Crazyness:_
* Doing it "just because they can".

### Video 2: Siemens

Scenarios and application domains:
* People recognition at entrance
* Navigation through building
* Tracking every person at every time
* Switching rooms with an elevator
* Central building controls

Technologies:
* Internet
* Holographic displays
* Floor sensors
* Power grids
* Building clusters
* Sensors for supply lines (water, electricity, ...)

Feasibility:
What might be doable?:
* People recognition using face recognition or other biometrics
* Navigation through building
* Central building controls

What not?
* Holographic displays
* Switching rooms with an elevator
* Tracking every person at every time

Weirdness/Crazyness:
* Privacy issues
* Elevator for rooms

### Video 3: Internet of Shrimps

Scenarios and application domains:
* Intelligent fridge
* Control over speech
* Surveillance
* Playing/Controlling instruments over internet

Technologies:
* Internet
* Cameras
* Step motor

Feasibility:
What might be doable?:
* Everything

Weirdness/Crazyness:
* The video was very weird in general. All the shown stuff is pretty useless and it's more like a homage.

## Internet of Things research

3 domains:
* Banking (smart payments, NFC, ...)
* Wearables (smart watches, health monitoring, fitness tracking)
* Retail (interaction with products, QR codes, amazon cashier free shop)
* Automotive
* Health care
* Assisted living

2 devices:
* Smart watches
* Amazon Echo

# 19.03.2018

## UlnoIot Setup

### Raspberry PI Setup

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#19032018)

I went through the tutorial from https://github.com/ulno/ulnoiot.

First I downloaded the image of ulnoiot and made sure the image was the right one by checking the SHA checksum. Then I flashed the image on the SD card with Etcher.

I changed the config.txt values uiot_ap_name: to mc_guys_3 and uiot_ap_password: to	mcguys123. After that I started the Raspberry and connected via ssh. Afterwards I had to change the password from ulnoiot to mcguys123. The next step was to upgrade the ulnoiot software and to expand the harddisk in raspi-config.

I was the only one with a mac in our team, but it was very easy to set things up.

### Configure Node1 and Node2

We had a problem to figure out which device node1 and node2 was so we wrote down the devices.

node1 = LED, node2 = Button

After figuring out which node was the LED and the Button another problem occured, for a while we thought the node was broken, because we could not connect to the node. But then we realized, that the node takes some time to boot.

# 22.03.2018

## What does the term H&B entail?
* Control home devices from remote
* Voice control
* Sensors
* Central hub where all devices are connected (gateway)
* Security
* Monitoring
* Entertainment
* Energy Efficiency
* Convenience

## UlnoIot Hello World

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#ulnoiot-hello-world)

Goal was to trigger a button to turn on/off LED on another Node.

The node setup was quite easy, because we already knew the commands. The hard part was to figure out the architecture behind our setup, because I was not familiar with the MQTT-Protocol and so i did not know what a MQTT-Broker was. But with the help of our Professor it became more clear.

## Advanced Hello World

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#relay)

Now we knew, how we can turn on/off a LED, we wanted to trigger a relay with a connected lock with our button. We used a 12V power supply for the relay, but after a short time it began to stank, but it all worked out.

# 23.03.2018

## RFID controlled lock

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#control-servolock-vai-a-rfid-reader)

First we setup the devices and then thought about, how we can trigger the lock with the RFID-Card. After some thinking we tried an approach with Node-Red. Oliver applied a function filter to get the ID of the card to check if the card is valid, after that, on/off was forwarded to another node to lock/unlock the lock.

## Showing temp/humidity on LCD-Display

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#showing-temphumidity-on-lcd-display)

The setup was quite easy, because we knew already the workflow. The focus laid on the MQTT-Forwarding. We had some troubles to show the combined two sensor values on the display, but with the help of the whole team we figured it out.

# 04.04.2018

## Home Assistant

I did the Home Assistant tutorial from the website https://www.home-assistant.io/getting-started/, but could not make it run.

## Project 1 - Discussion Round

Discussion about home and automation building topics. First we brainstormed and wrote our thoughts on a whiteboard afterwards we provided a video where a moderator and two pro and con members discussed these topics.

In the lecture we discussed these topics in groups of moderators, pro and the con teams. I was in the con team and was part of the discussion panel. We had to defend our arguments against the pro team. After each topic the audience prepared some questions we had to answer.  

### Notes

* Moderator
	* Good introduction
* Pro
	* Well prepared
	* Opening statement to long
* Con
	* Clear statement
	* Straight to the point

#### Questions
* How much will collected data influence eg. insurances for elderly people?
* Is there a misuse of collected data /tracking in public places / buildings?
* Can home automation be a benefit for action forces like police, fire brigade?
* With home automation elderly people will get lazy. Is that so good for their health hand fitness if they have no effort at all?
* Lot of different home automation systems, is there a change for a single standard?
* Alexa starts recording after the keyword? How is the keyword recorded then? (unclearly stated from pro team)

## Protocols and research

There were about 10 protocols, so we split into groups of two and made a presentation about one protocol. Rosemarie and I were responsible for KNX and Ebus. After the presentation I had a better understanding about the different protocols. My favourite protocols were Zigbee, Zwave and SPI.

### Zigbee
* Mesh network
* Eg. Hue bulb
* Controller/Router/End Devices

### Z-wave
* Mesh network
* Less power than Bluetooth
* Low latency

### rs-232
* Communication between terminals
* Replaced by USB
* Slow rates

### rs-422
* Successor of rs-232
* Temperature controllers
* 10 Mbit/s
* Can communicate back (but scheduling needed)
* Eg. controlling video surveillance

### DMX
* Eg. stage lights and effects
* No error handling
* Max. 300m

### SPI
 * Full Duplex Mode
 * Master - Slave (single master)
 * Camera lenses

### I2C
* Serial
* Half Duplex
* Master - Slave (multi master)
* Only 2 bus lines

### OneWire
* Bus system
* 1-wire
* Multiple slaves accessed using 2-wires
* Easy to implement
* Slower

### X10
* Communicates via power line --> slow
* Home automation domain
* Cheap
* Usage: hybrid system with Zigbee or Z-wave
* Eg. Dimmer
* Popular

### KNX
* 2-wire bus
* Tree/Line/Star topology
* Eg. Shutter, alarm monitoring,lighting,..
* Eg. Home and building automation

### Ebus
* 2-wire digital serial data-bus communication interface
* 100m
* Master - Master / Master - Slave

### Canbus
* For automotive to save copper
* Mostly commonly used in vehicles
* Not so important for home automation
* Multi-master serial bus
* 2-wire

### Modbus
* Serial communication protocol
* Flexible
* Also used for smart grids
* Not so important for home automation

### BACnet
* Communication of multiple devices across buildings
* Objects used to represent aspects of control system
* 54 different object types
* Services for information exchange
* Systems from various vendors

## Project 2 - Automate your friends home

[Project 2](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project2)

The scenario was to automate a friends home. We wrote about the daily routine of a fictional friend. The result was quite satisfactory.
Next step is to provide a shopping list of devices and gadgets for the home automation system.

# 10.04.2018
## KNX certificate

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#knx-certificate)

Quite easy, no further issues. Certificate can be found ([here](https://github.com/PiotrSwietek/MC-Guys/tree/master/Portfolios/Manuel%20Mühlschuster)).

## MQTT Simulator

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#mqtt-simulator)

Goal was to program an MQTT-Simulator to simulate devices we don't have. We used Node-Red for this exercise.

## Philips HUE Lamp

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#philips-hue-lamps)

Goal was to control Philips HUE Lamp over the Raspberry PI. First we had to setup a Wifi-usb-adapter to the hue-bridge to get an internet connection, because control the hue-bridge over the ethernet port and therefore don't have an active internet connection. We had some troubles with the HUE Lamp, but could solve them by shut down the PI connect the HUE Lamp and restart the PI.

This Part was mainly done by Piotr, but i looked at the setup and Node-Red to get an understanding of what he was doing.

## Kodi

[Protocol](https://github.com/PiotrSwietek/MC-Guys/blob/master/Protocol/Protocol.md#kodi)

The Kodi part was mainly done by Oliver, but Oliver showed me how i can setup and use Kodi.

# 17.04.2018

## Project 2

[Project 2](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project2)

Some notes and questions about the project 2 presentations

* ENI (Internationals)
 * Why Amazon Echo? What about Google, etc.?
 * NFC card vs fingerprint? I would have some security concerns...
 * Own apps are overkill for your friends house

* ENI
 * Nice mini server expanples, detailed presentation, but too long presentation
 * Could be a tech presentation...
 * Are there only loxone components to integrated? What about Homematic devices, etc.?

## Snowboy

I did the Snowboy tutorial on a mac not on the PI from the website https://snowboy.kitt.ai.

# 19.04.2018

## Project 3

[Project 3](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project3)

We decided to realise the scenario, we have already described in [Project 2](https://github.com/PiotrSwietek/MC-Guys/tree/master/Projects/project2).

# 26.04.2018

## Project setup

Bernhard, Denis and I did nearly the whole node stuff. We flashed following nodes:

* Servo (Shutter, Windows,...)
* Button
* Multi RGB
* Lock
* Humiture Sensor

Bernhard and I were responsible for voice control. After trying different approaches with Snowboy, Bernhard tried the voice control via the Google Assistant, IFTTT and Adafruit. He got it working and by triggering an mqtt message by saying "Movie mode" the IFTTT application sends the data to Adafruit and the MQTT broker listens via Node Red on the Adafruit changes/events.

Some notes about the other group presentations:

* ENI
 * Cool timing idea, going through the whole day in fast motion
 * Nice DYI smart water boiler
 * Good presentation

* ENI (Internationals)
 * Why no live demo?
 * Lot of things they played around with and tried out
 * Not that related to their use cases

# Course Reflection

I really liked this course, because at the beginning of it, I had no understanding, of how all the devices/nodes were connected and how they interact with each other to build a Home Automation System. The UlnoIot Raspberry ROM made it quite simple to interact with these different devices/nodes. I also liked the parts, where we had to figure out things on our own. What I didn't like about this course is the matrix chat, because we often missed some chat details and/or deadlines.
