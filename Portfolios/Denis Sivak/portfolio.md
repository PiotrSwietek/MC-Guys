# Lecture 1 (19.03.2018)

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
[(Link to protocol)](../../Protocol/Protocol.md#ulnoiot-environment-setup)

	* Setup Raspberry Pi with the UlnoIoT image
	* Initialized and setup Wemos D1 mini
	* Controlling onboard-LED of the Wemos using the Raspberry Pi
	* Connection of external button to Wemos D1 mini
	* Reading the buttons value in the Raspberry Console
	
## Problems during the practical stuff
	* One problem we had was that we didn't knew how to get the actual value of the button
	* Also defining the mqtt action was problematic as we did not understand all the parameters
	
## Lecture reflection
This lecture I learned what the terms IoT and H&B-Automation denote. It was also very interesting for me to work with a Raspberry PI because I have never done that before and
I really looked forward to it.
I really liked how ulno-iot is implemented and how easy it is to configure a node.

# Lecture 2 (22.03.2018)

### What does the term entail?
	* Remote control of building environment
	* Automation of  building environment using sensors (lights, heating, air conditioning, ...)
	* Monitoring (water, current, ...)
	* Energy efficiency
	* Convenience
	* Security
	
## Summary of practical stuff done
[(Link to protocol / wemos setup)](../../Protocol/Protocol.md#ulnoiot-hello-world)
[(Link to protocol / doorlock)](../../Protocol/Protocol.md#relay)

	* Setting up a second Wemos D1 mini node
	* Configuring button and LED as devices
	* Using mqtt to add an action for the button press
	* The LED can now be controlled remotely using the button
	* Setting up Node RED to toggle the led using a button
	* Implemented doorlock to open with GUI buttons using Node RED 
	
## Lecture reflection
This lecture I learned how to use different devices with the Wemos D1 mini nodes. I was surprised how easy it actually is to setup everything with ulno-iot but I would also like
to get a bit more insight on how it really works and what happens in the background.

# Lecture 3 (23.03.2018)

## Summary of practical stuff done
[(Link to protocol / rfid reader)](../../Protocol/Protocol.md#Control-servo)
 [(Link to protocol / dht22 & display)](../../Protocol/Protocol.md#Showing-temp)

	* Setting up the door lock using an RFID card reader 
	* Setting up a temperature and humidity sensor
	* Connecting the LCD display 
	* Display of sensor data (temperature and humidity) on the LCD
	
## Problems during the practical stuff
	* Connecting and setting up the servo was quite confusing 
	
## Lecture reflection
This lecture we had some problems using the servo because there are different parameters/angles to configure which are not very well documented. We had to ask the professor for help because
we did not understand what all those angles actually mean/do.

# Lecture 4 (03.04.2018)

## H&B Discussion: 
	* Should everybody use home & building automation?
	* Elderly people could have problems because its too complex
	* Costs? Installation, Configuration, Maintenance
	* Security and Privacy issues
	* Using H&B can also help elderly or disabled people
	* Centralized control helps gaining convenience and comfort
	
## Bus & Protocol research

### SPI: Serial Peripheral Interface

* Synchronous serial communication (shared CLK)
* Full Duplex mode using master-slave architecture (single master)
* Slave select line to support multiple slave devices

#### 4 wires:
	Clock (CLK)
	Master Output Slave Input (MOSI)
	Master Input Slave Output (MISO)
	Slave Select (SS)

#### Speed & Throughput:
	The maximum throughput of the SPI will be limited by one of three factors: 
	1.) Maximum available SPI clock
	2.) Ability of CPU to service SPI data.
	3.) Output driver strength (how fast a signal can the PCB carry)
	
#### Latency:
	Can be as low as one clock cycle.

#### Length:
	8-bit register indicates the SPI frame length (16, 24, or 32 bit)

#### Importance:
	* de facto standard for short distance communication
	* primarily used in embedded systems

#### Usage Example:
	* Used to talk to a variety of peipherals
		* Sensors
		* Memory
		* LCDs
		* Camera lenses
		* ....
	* RFID reader we used in the lecture

#### Domain:
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

## Lecture reflection
What I hated in this lecture was that I had to argue against H&B automation in the discussion round. It's really hard to make something look bad if you actually don't think so. 
Sometimes I felt kinda stupid because I had to come up with arguments that don't really make sense just to satisfy the discussion.
Overall I think it was quite fun for everybody to see different viewpoints on the topic and how everything has it's pros and cons.

# Lecture 5 (10.04.2018)

## KNX eCampus
[(Link to certificate)](./knxcertification.pdf)

In the beginning of the lecture, we started the KNX eCampus which is basically a set of tutorials for the use of the KNX bus/protocol. The tutorials also include
simulations and quizzes which had to be completed. After completing all of the tutorials, a KNX certificate is achieved. 
Personally I found that the tutorial was very simple but it showed the basic usage and setup of the software with the devices which could be useful in the future.

## MQTT Simulator
[(Link to protocol)](../../Protocol/Protocol.md#mqtt-simulator)

For this task we used node RED. Therefore, a button was added to the UI which sends a message to the mqtt broker on the PI. When the PI receives the message, the signal
is forwarded to the PC, which then plays an audio file.

## Lecture reflection
This lecture I really did not like the KNX eCampus because I think that I haven't learned anything from it I can use in the future. If I'm going to use KNX one day, I will for sure have to 
do the tutorial again and get more information. Doing an online tutorial for something you cannot actually use wasn't that fun.

# Project 2
For this project we had to plan the automation of our friends home. I was responsible for the climate & heating part. I decided to use only HomeMatic devices because the
structure of their homepage was more appealing to me than the ones from other manufacturers. The needed components could be found easily and well-described on their homepage.
What I also liked is that it was able to filter for different applications (lights, heating, entertainment) which made it quite easy to plan accordingly.

In this project I learned how easy it can be to automate your home if you have money. The sophisticated and well-planed solutions that were presented by the teams were very expensive
(<50000 €) but they also seemed easy to integrate and well designed. The cheaper and DIY solutions didn't seem to be as manageable.

# Project 3
For this project we had to a prototype system for a defined automation scenario. My role in the team was the configuration of all nodes and some interactions on Node-RED. 

This project showed me that integrating many nodes can be problematic and harder to manage. Also we had some problems with the voice control in the beginning but in the end
we managed to get it working. The live-presentation also worked out well.

# Course reflection
I really liked the way it was taught. We did much practical stuff and learned many things by doing. Also we could always ask for help if we had some problems to get a more detailed explanation
on the topic. 
The thing I hated the most about the course is that we did not use the Moodle platform. Basically every course at the FH is managed via the Moodle system and all students are used to it. It is quite
confusing if one course is managed via different platforms. Providing all the necessary material and information via Moodle would have been so much more convenient for the students.
All in all I enjoyed the lessons and the information provided. I now understand how such systems work and how the nodes interact with each other. Also the second project was probably the thing
I liked the most about this course because I got insight on how you would plan and realize such systems in real life. 