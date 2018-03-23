# Portfolio for H&B Automation class

## Introduction

My name is Denis and I'm studying Mobile Computing because I like computers and I fell into the "mobile generation" 
so I thought it would be a good idea.
I'm expecting/hoping to learn which devices/controllers are used, how they work and communicate and especially how to work
with Raspberry PIs because I have never used them before. Also H&B automation is getting more and more attention these days 
so I thought it would be kind of important to take this class.

## Summaries of the shown videos

### Video 1: Big Bang Theory Snippet

#### Scenarios and application domains:
	* Control Lights, Stereo, RC vehicles
	* (Public) Access over internet

#### Technologies:
	* Internet

#### Feasibility:
##### What might be doable?:
	* Controlling electronic devices over the internet
		
##### What not?
	* Everything shown is possible up to date.

#### Weirdness/Crazyness:
	* Doing it "just because they can".
	
### Video 2: Siemens

#### Scenarios and application domains:
	* People recognition at entrance
	* Navigation through building
	* Tracking every person at every time
	* Switching rooms with an elevator
	* Central building controls

#### Technologies:
	* Internet
	* Holographic displays
	* Floor sensors
	* Power grids
	* Building clusters
	* Sensors for supply lines (water, electricity, ...)

#### Feasibility:
##### What might be doable?:
	* People recognition using face recognition or other biometrics
	* Navigation through building
	* Central building controls
		
##### What not?
	* Holographic displays
	* Switching rooms with an elevator
	* Tracking every person at every time

#### Weirdness/Crazyness:
	* Privacy issues
	* Elevator for rooms

### Video 3: Internet of Shrimps

#### Scenarios and application domains:
	* Intelligent fridge
	* Control over speech
	* Surveillance
	* Playing/Controlling instruments over internet

#### Technologies:
	* Internet
	* Cameras
	* Step motor

#### Feasibility:
##### What might be doable?:
	* Everything

#### Weirdness/Crazyness:
	* The video was very weird in general. All the shown stuff is pretty useless and it's more like a homage.

## Internet of Things research

### 3 domains:
	* Banking (smart payments, NFC, ...)
	* Wearables (smart watches, health monitoring, fitness tracking)
	* Retail (interaction with products, QR codes, amazon cashier free shop)
	* Automotive
	* Health care
	* Assisted living
	
### 2 devices:
	* Smart watches
	* Amazon Echo
	
## Summary of practical stuff done
	* Setup Raspberry Pi with the UlnoIoT image
	* Initialized and setup Wemos D1 mini
	* Controlling onboard-LED of the Wemos using the Raspberry Pi
	* Connection of external button to Wemos D1 mini
	* Reading the buttons value in the Raspberry Console
	
## H&B Automation (22.03.2018)

### What does the term entail?
	* Remote control of building environment
	* Automation of  building environment using sensors (lights, heating, air conditioning, ...)
	* Monitoring (water, current, ...)
	* Energy efficiency
	* Convenience
	* Security
	
## Summary of practical stuff done
	* Setting up a second Wemos D1 mini node
	* Configuring button and LED as devices
	* Using mqtt to add an action for the button press
	* The LED can now be controlled remotely using the button
	* Setting up Node RED to toggle the led using a button
	* Implemented doorlock to open with GUI buttons using Node RED