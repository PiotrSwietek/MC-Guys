# Portfolio - Home and Building Automation
## Mobile Computing Master - SS 2018


## whoami
My name is Oliver Barth. I come from small town called Vorderweißenbach (30km north to Linz). I did my Bachelor in Mobile Computing in 2017 and currently running the Mobile Computing Master Program.
* Why in this master program?
Lot of modules to choose from, program with the most interesting lectures (in my opinion).

* Expectations H&B?
Do (and see) some cool projects. Understand what's behind the scenes (sensors, actors, architecture, ...)

* Strength/weakness myself?
Strength: Quite good at bringing a project to code (paper).
Weakness: Not that creative, hate writing documentations (especially if has to happen afterwards).

## Video session
* Scenarios
Big bang theory: typical home automation
Siemens: life in the future, space control, intelligent routing, energy efficiency, security
* Technology
Big bang theory: Satellite, smartphone, laptop
Siemens: interactive hologram, light barriers for entry policy (open door principle), plug-in of whole room, distributed grid (intelligent network), personal navigation (smartphone, walls), intelligent light (different modes) e.g. for emergency, interactive floor to mark traces, IT-backbone for clustering buildings
Internet of shrimps: voice control
* Feasibility
Big bang theory: using satellite for home automation (too expensive)
Siemens: no interactive hologram in time
* Weirdness/craziness
Big bang theory: remote switch for lightning, sending signal all over the world,
Siemens: controlling/monitoring everything (privacy concerns), movable offices

## Internet of things
* What does the Inernet of Things entail?
"The Internet of things (IoT) is the network of physical devices, vehicles, home appliances and other items embedded with electronics, software, sensors, actuators, and connectivity which enables these objects to connect and exchange data" - Wikipedia

* Provide 3 domains
Agriculture
Smart factory
Medical and health care
Assisted living

* Provide 2 typical devices (appliance or controller)
micro-controller (arduino), smartphones, smart watches, trackers,  hue light bulb from Phillips, ...


## UlnoIoT FirstSteps
Goal is to get familiar with the UlnoIoT-Framework. 
The Raspberry-Pi works as a Wireless-Router. The nodes can then connect to the Pi automatically and can talk to it via the MQTT-Protocoll. So the Pi is basically a central broker for all the nodes.

### Setup
The Raspberry-Pi got flashed with an image provided from .... The image contains all the predefined software to flash and configure the nodes, which are later used to get some input/output of our home automation system.
To flash the Pi we used the Etcher software. This is a free online tool to make the image bootable from a SD-card.
Before booting, we have to configure some files to get our own Wifi running (SSID and pwd).

After successful boot up, the configured Wifi should be visible and can be connected to. the Pi can be remote accessed via SSH. The used terminal is called MobaXterm.


