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

_Scenarios and application domains:_
	* Control Lights, Stereo, RC vehicles
	* (Public) Access over internet

_Technologies:_
	* Internet

_Feasibility:_
What might be doable?:
	* Controlling electronic devices over the internet

What not?
	* Everything shown is possible up to date.

_Weirdness/Crazyness:_
	* Doing it "just because they can".

### Video 2: Siemens

_Scenarios and application domains:_
	* People recognition at entrance
	* Navigation through building
	* Tracking every person at every time
	* Switching rooms with an elevator
	* Central building controls

_Technologies:_
	* Internet
	* Holographic displays
	* Floor sensors
	* Power grids
	* Building clusters
	* Sensors for supply lines (water, electricity, ...)

_Feasibility:_
What might be doable?:
	* People recognition using face recognition or other biometrics
	* Navigation through building
	* Central building controls

What not?
	* Holographic displays
	* Switching rooms with an elevator
	* Tracking every person at every time

_Weirdness/Crazyness:_
	* Privacy issues
	* Elevator for rooms

### Video 3: Internet of Shrimps

_Scenarios and application domains:_
	* Intelligent fridge
	* Control over speech
	* Surveillance
	* Playing/Controlling instruments over internet

_Technologies:_
	* Internet
	* Cameras
	* Step motor

_Feasibility:_
What might be doable?:
	* Everything

_Weirdness/Crazyness:_
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

# UlnoIot Setup

## Raspberry PI Setup

I went through the tutorial from https://github.com/ulno/ulnoiot.

First I downloaded the image of ulnoiot and made sure the image was the right one by checking the SHA checksum. Then I flashed the image on the SD card with Etcher.

I changed the config.txt values uiot_ap_name: to mc_guys_3 and uiot_ap_password: to	mcguys123. After that I started the Raspberry and connected via ssh. Afterwards I had to change the password from ulnoiot to mcguys123. The next step was to upgrade the ulnoiot software and to expand the harddisk in raspi-config.

## Configure Node1 and Node2

We had a problem to figure out which device node1 and node2 was so we wrote down the devices.

node1 = LED, node2 = Button

After figuring out which node was the LED and the Button another problem occured, for a while we thought the node was broken, because we could not connect to the node. But then we realized, that the node takes some time to boot.

## Node Red

Node Red is a programming tool for wiring together hardware devices.
