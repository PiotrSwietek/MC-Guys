# Lecture 1

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
	
## Problems during the practical stuff
	* One problem we had was that we didn't knew how to get the actual value of the button
	* Also defining the mqtt action was problematic as we did not understand all the parameters
	
# Lecture 2

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
	
## Problems during the practical stuff
	
	
# Lecture 3

## Summary of practical stuff done
	* Setting up the door lock using an RFID card reader
	* Setting up a temperature and humidity sensor
	* Connecting the LCD display 
	* Display of sensor data (temperature and humidity) on the LCD
	
## Problems during the practical stuff
	* Connecting and setting up the servo was quite confusing 

# Lecture 4

## H&B Discussion: 
	* Should everybody use home & building automation?
	* Elderly people could have problems because its too complex
	* Costs? Installation, Configuration, Maintenance
	* Security and Privacy issues
	
## Bus & Protocol research

### SPI: Serial Peripheral Interface

* Synchronous serial communication (shared CLK)
* Full Duplex mode using master-slave architecture (single master)
* Slave select line to support multiple slave devices

4 wires:
	Clock (CLK)
	Master Output Slave Input (MOSI)
	Master Input Slave Output (MISO)
	Slave Select (SS)

Speed & Throughput:
	The maximum throughput of the SPI will be limited by one of three factors: 
	1.) Maximum available SPI clock
	2.) Ability of CPU to service SPI data.
	3.) Output driver strength (how fast a signal can the PCB carry)
	
Latency:
	Can be as low as one clock cycle.

Length:
	8-bit register indicates the SPI frame length (16, 24, or 32 bit)

Importance:
	* de facto standard for short distance communication
	* primarily used in embedded systems

Usage Example:
	* Used to talk to a variety of peipherals
		* Sensors
		* Memory
		* LCDs
		* Camera lenses
		* ....
	* RFID reader we used in the lecture

Domain:
	* Embedded systems

### Other busses & protocols
	* RS232, RS442, RS485, DMX
	* Onewire/X10
	* Zwire/ZigBee
	* KNX-bus/E-bus
	* Modbus/CANbus
	
### Favorite busses & protocols
	* SPI
	* I2C
	* ZigBee
	
## OpenHAB
We tried to get OpenHAB running. Unfortunately, we had some problems on our machines which cost too much time, so we didn't finish the OpenHAB stuff in time.
	
# Lecture 5

## KNX eCampus
In the beginning of the lecture, we started the KNX eCampus which is basically a set of tutorials for the use of the KNX bus/protocol. The tutorials also include
simulations and quizzes which had to be completed. After completing all of the tutorials, a KNX certificate is achieved. 
Personally I found that the tutorial was very simple but it showed the basic usage and setup of the software with the devices which could be useful in the future.

## MQTT Simulator
A temperature sensor was simulated by creating a UI slider in Node-RED. The slider value sets the actual temperature to be broadcasted over mqtt.
For that, we had to install Node-RED locally on our machines. We learned that it has to be installed via the Windows Powershell using the command
"npm install -g --unsafe-perm node-red". Before that, Node-JS has to be installed for it to work.
One of the problems we had to create a (local) server where the actual messages from the simulator are received. 

## 