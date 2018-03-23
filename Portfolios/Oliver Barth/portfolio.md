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

## Projectteam/Git setup
Before we continue with our first practical work, we have to setup a team and a git repository, so everyone can share their knowledge and code.
The setup was quite easy, although there was some problems with SourceTree regarding the login. In fact, you could not login with username and password (and I don't know why, it always worked before). Piotr had the same issues, so this is obviously a bug within SourceTree itself. Switching to SSH-keys (which should always be the best choice concerning security and convenience) to access the repo fixed the problem.

## UlnoIoT FirstSteps
Goal is to get familiar with the UlnoIoT-Framework. 
The Raspberry-Pi works as a Wireless-Router. The nodes can then connect to the Pi automatically and can talk to it via the MQTT-Protocoll. So the Pi is basically a central broker for all the nodes.

### Setup
The Raspberry-Pi got flashed with an image provided from .... The image contains all the predefined software to flash and configure the nodes, which are later used to get some input/output of our home automation system.
To flash the Pi we used the Etcher software. This is a free online tool to make the image bootable from a SD-card.
Before booting, we have to configure some files to get our own Wifi running (SSID and pwd).
The setup was quite easy, so we can now (for the first time) boot up our Pi.

After successful boot up, the configured Wifi should be visible and can be connected to. the Pi can be remote accessed via SSH. The used terminal is called MobaXterm.
MobaXterm is quite is to use (you can actually open files in an kind of remote editor) and so there appeared no problems at all.

### Our first node
The next task was to create our first node which should be able to (automatically) connect to the Pi. With the Pi and the remote shell, we can than connect to the node and execute some local commands, e.g. to let a onboard led turn on/off.
My part was the whole configuring on the Pi with the help of the others.
Working with the terminal needed some time to get familiar with the commands and behavior. After that navigating and copying files (configuration for the node) around worked out well.
Flashing the node with the copied configuration only needs one command ("initialize" - quite easy and convenient). 
After successful flashing and connecting to another computer via usb we had some troubles connecting to the node via the Pi-shell. There was always a connection error. The reason for that was that we need to wait about 30 seconds to let the node boot up and connect to the Pi. After some trial and error we made out that behavior. Note to myself: be a little bit more patient.