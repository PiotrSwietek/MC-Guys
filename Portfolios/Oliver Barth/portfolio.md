# Portfolio - Home and Building Automation
Mobile Computing Master - Summer term, 2018

## whoami
My name is Oliver Barth. I come from small town called Vorderweißenbach (30km north to Linz). I did my Bachelors Degree in Mobile Computing in summer 2017 and I am currently enrolled in the Mobile Computing Masters Program.

### Why am I in this master program?
Lot of modules to choose from, program with the most interesting lectures (in my opinion).

### Expectations H&B?
Do (and see) some cool projects. Understand what's behind the scenes (sensors, actors, architecture, ...)

### Strength/weakness myself?
Strength: Quite good at bringing a project to code (paper).
Weakness: Not that creative, hate writing documentations (especially if has to happen afterwards).

## Video session
### Scenarios shown
* Big bang theory

   Typical home automation
* Siemens

   Life in the future, space control, intelligent routing, energy efficiency, security
### Technology
* Big bang theory

   Satellite, smartphone, laptop
* Siemens

   Interactive hologram, light barriers for entry policy (open door principle), plug-in of whole room, distributed grid (intelligent network), personal navigation (smartphone, walls), intelligent light (different modes) e.g. for emergency, interactive floor to mark traces, IT-backbone for clustering buildings
* Internet of shrimps

   Voice control
### Feasibility
* Big bang theory

   Using satellite for home automation (too expensive)
* Siemens

   No interactive hologram in time
### Weirdness/craziness
* Big bang theory

   Remote switch for lightning, sending signal all over the world
* Siemens

   Controlling/monitoring everything (privacy concerns), movable offices

## Internet of things
### What does the Inernet of Things entail?
Definition from Wikipedia (https://en.wikipedia.org/wiki/Internet_of_things)
> The Internet of things (IoT) is the network of physical devices, vehicles, home appliances and other items embedded with electronics, software, sensors, actuators, and connectivity which enables these objects to connect and exchange data.


### Provide 3 domains
* Agriculture
* Smart factory
* Medical and health care
* Assisted living

### Provide 2 typical devices (appliance or controller)
* Micro-controller (e.g. arduino)
* Smartphones
* Smart watches
* Trackers
* Hue light bulbs from Phillips
* ...

## Projectteam/Git setup
[(Protocol)](../../Protocol/Protocol.md#project-setup)

Before we continue with our first practical work, we have to setup a team and a git repository, so everyone can share their knowledge and code.
The setup was quite easy, although there was some problems with SourceTree regarding the login. In fact, you could not login with username and password (and I don't know why, it always worked before). Piotr had the same issues, so this is obviously a bug within SourceTree itself. Switching to SSH-keys (which should always be the best choice concerning security and convenience) to access the repo fixed the problem.

## UlnoIoT environment setup
[(Protocol)](../../Protocol/Protocol.md#ulnoiot-environment-setup)

Goal is to get familiar with the UlnoIoT-Framework. 
The Raspberry-Pi works as a Wireless-Router. The nodes can then connect to the Pi automatically and can talk to it via the MQTT-Protocoll. So the Pi is basically a central broker for all the nodes.

### Setup
The Raspberry-Pi got flashed with an image provided from our professor and can be found here: (https://goo.gl/bVgLMr). The image contains all the predefined software to flash and configure the nodes, which are later used to get some input/output of our home automation system. Interesting for me would have been what software/framwworks etc. are on the image and how to build something like that.

To flash the Pi we used the Etcher software. This is a free online tool to make the image bootable from a SD-card.
Before booting, we have to configure some files to get our own Wifi running (SSID and pwd).
The setup was quite easy, so we can now (for the first time) boot up our Pi.

After successful boot up, the configured Wifi should be visible and can be connected to. The Pi can be remote accessed via SSH. The used terminal is called MobaXterm.
MobaXterm is quite easy to use (you can actually open files in an kind of remote editor) and so there appeared no problems at all.

### Our first node
[(Protocol)](../../Protocol/Protocol.md#iot-nodes)

The next task was to create our first node which should be able to (automatically) connect to the Pi. With the Pi and the remote shell, we can than connect to the node and execute some local commands, e.g. to let a onboard led turn on/off.
My part was the whole configuring on the Pi with the help of the others.
Working with the terminal needed some time to get familiar with the commands and behavior. After that navigating and copying files (configuration for the node) around worked out well.
Flashing the node with the copied configuration only needs one command (`initialize` - quite easy and convenient). After some discussions I found out that as kind of operating system *MicroPython* was used (https://micropython.org/). But there are still some open questions (and maybe also interesting for the others): *What is MicroPython at all, why are we using this, what are the alternatives?*

After successful flashing and connecting to another computer via usb we had some troubles connecting to the node via the Pi-shell. There was always a connection error. The reason for that was that we need to wait about 30 seconds to let the node boot up and connect to the Pi. After some trial and error approaches we made out that behavior. Note to myself: be a little bit more patient.

One of the hardest steps was actually getting the commands right to register a device, and of course finding out what that actually means and what it does in the background. One accentual thing we missed in the beginning, the `run()` command after we finally figured out how to register a device.

### UlnoIoT Hello World
[(Protocol)](../../Protocol/Protocol.md#ulnoiot-hello-world)

Goal is to set up a "Hello World program" in the sense of home automation: Triggering a button of one node turns a LED on/off on the other node.

Setting up the nodes was quite easy because we already knew the commands needed. The big question was, how to set up the connection to forward the button signal to the other node. With the help of our team-mates, we finally figured that out. Understanding the architecture behind our setup (Pi is our MQTT-broker as well) and what that means was not that clear for the others and myself, because we were fairly unfamiliar with the MQTT-protocol. Fixing it with the short intro from our professor inbetween made that more clear for us all.

### Advanced Hello World
[(Protocol)](../../Protocol/Protocol.md#relay)

Because triggering the onbard LED was an quite simple task, we want to trigger a relay with a connected lock with our button.
We only had to set up the relay on our controller and wiring all together. For the relay we used 12V power supply. But we nearly burned the thing up (it already began to stank) because obviously the voltage was too high. Maybe we should attach a label on it to prohibit such mistakes.

### RFID controlled lock
[(Protocol)](../../Protocol/Protocol.md#control-servolock-vai-a-rfid-reader)

For that task I was responsible for extending our protocol and wiring up the RFID-reader on our controller. Thanks to the docs from our professor no problems occured.
Together we set up all devices. The main question was how we can trigger the lock with an RFID-card? We could not simply forward the input from the card to the other node, there must be some logic in between. Because we do not want to code (look for the right console-commands), we used *Node-RED* for that task. 

After getting through some basic tutorials (and I think that was absolutely neccesary to get an idea what is going on) I finally set up a function to filter out the ID of the card to check if it is a valid one and then forwards on or off to the other node. 

### Showing temp/humidity on LCD-display
[(Protocol)](../../Protocol/Protocol.md#showing-temphumidity-on-lcd-display)

Again I was responsible for extending the protocol. 
Now that we are getting more and more familiar with *Node-RED*, there was this advanced exercise for us. Setting up devices was quite easy that time, the focus lay on the MQTT-fowarding stuff. I was quite unsure what functions we should use for our problem, because we needed to combine the two sensor values and clearing somehow the display if new messages arrive. After some trial and error approaches and the help of our team-mates, we finally made it togehter.

### Off topic
[(Protocol)](../../Protocol/Protocol.md)

Because I found out there is a special formatting sign for code snippets in markdown, I changed all the snippets inside the protocol to that formatting. Looks quite fancy now.

### Project 1 - Discussion round
Goal of this project was to get into an discussion about home and building automation topics.
First of all we provided a video in our team, where there was a moderator (me), two pro and two con members. Because none of the others wanted to be moderator, I volunteered (what saved me from the big discussion round the next session). After notating three topics and the corresponding pro and con arguments on a whiteboard, the video recording was straightforward altough we all were quite unfamiliar with such discussion groups.

The next part was a big discussion round in the lecture. Our team was the con, the other two teams split up into moderator and pro team.
For this I brain-stormed some con arguments for the topics provided by the moderator team in order to be prepared for the lecture. Because I was the moderator in the video the week before, I was out of discussion for that round, so I gave my notes to Manuel and Denis.
I was a member of the audience then, below some notes and questions fro my side:

#### General notes per team
* Moderator
   * Good inttroduction from Mona
   * Nice wrap ups (summaries) from both

* Pro
   * Nice picture of home automation
   * 15min to set up a home automation system? Quite optimistic...
   * Too much input for an opening statement
   * Nice counterattack to con-privacy issue
   * Well prepared

*  Con
   * Short but precise on securtiy issues
   * Clear statements (specializations) of both members
   * Quickly got to the heart of the issues

#### Questions
* How much will collected data influence eg. insurances for elderly people?
* Is there a misuse of collected data /tracking in public places / buildings?
* Can home automation be a benefit for action forces like police, fire brigade?
* With home automation elderly people will get lazy. Is that so good for their health hand fitness if they have no effort at all?
* Lot of different home automation systems, is there a change for a single standard?
* Alexa starts recording after the keyword? How is the keyword recorded then? (unclearly stated from pro team)

### Bus-Protocols
All in all there were about 10 different protocols which we should provide a small presentation on. We split up in groups, Piotr and I were responsible for rs-232, rs-422, rs-485 & DMX. After all the presentations I gained a really good overview about all the different protocols. Perfect teaching method for such things I think.

### Project 2 - Automate your friends home
We nearly missed the deadline for writing our scenario about our friends home automation system. But the result was quite satisfactory.
Next step is to provide a shopping list of devices and gadgets for the home automation system.

### KNX certificate
[(Protocol)](../../Protocol/Protocol.md#knx-certificate)

Quite easy, no further issues.
Certificate can be found [(here)](knxcertification_barth.pdf).

### HUE lamp & Kodi
HUE [(Protocol)](../../Protocol/Protocol.md#philips-hue-lamps)

Goal was to set up the Philips HUE lamps and control it over the Pi. Because we control the hue-bridge over the ethernet port we have no active internet connection. So the first thing have to set up a Wifi-usb-adapter to bridge the internet connection. That causes some troubles, we do not got some internet connection, that was quite frustrating for me. At least we could control the HUE lamp locally from our computers. Maybe we introduce some disco light next lession. 

Kodi [(Protocol)](../../Protocol/Protocol.md#kodi)

Kodi is an entertainment platform which we also should control over MQTT over node-RED. There is a node-RED plugin available which provides own nodes for the interface and uses RPCs to control Kodi, but there were some connection issues in node-RED, although Kodi was accessable via a web interface. After some trial-and-error approaches, I swapped to a plugin for Kodi itself which listens and sends out MQTT-messages for some basic actions.

### Project 2
[(Project 2)](../../Projects/project2)

Some notes and questions about the project 2 presentations
* ENI (Internationals)
   * Why Amazon Echo? What about Google, etc.?
   * NFC card vs fingerprint? I would have some security concerns...
   * Own apps are overkill for your friends house

* ENI
   * Nice mini server expanples, detailed presentation, but too long presentation
   * Could be a tech presentation...
   * Are there only loxone components to integrated? What about Homematic devices, etc.?

### Hue lamp & Kodi continued
Kodi [(Protocol)](../../Protocol/Protocol.md#kodi)

After some issues last session, I worked on the Kodi setup with the MQTT plugin. I was quite confident that the node-red flow was correct, but it didn't worked either. After double check all the configuration, I restarted the Kodi platform and it finally worked. 90% working on that was a waste of time I guess.

HUE [(Protocol)](../../Protocol/Protocol.md#philips-hue-lamps)

After setting up Kodi, I helped Piotr with the Hue lamps. Now the new setup works very well, but the node-Red flow was tricky that time. Because we want to control all the possible hue stuff stuff, the configuration becomes quite complex (see protocol), but we finally made it. And after all, for me it was quite funny to play around with them.

### Project 3 - in class
Because of the reschedule of the our time table, I was not able to attend to this lesson. I informed both my team mates and the professor. Glad that for both of them it was not a problem at all.

### Project 3 - meetings
[(Project 3)](../../Projects/project3)

Goal of the project was to implement some usage scenarios from our project 2 when we automated our friends home. Because our usage scenario was already very well set up, we just splitted it into different sections. 

We met for two days to build the final project. Because we wanted to use stuff we already did in the lecture, finding the right work packages was quite easy for us: everyone does what he has already done (see [Work packages](../../Projects/project3/work-packages.PNG). This decision speed up our implementation a lot.

Besides our main responsibilities, everyone had time to help the other one out if there occured any problems. For me that was kind of a good feeling, I think that this is just the way a project like this should be handled. Fast decision making, flexible and after all, a high quality. And basically, the initial work packages has changed, so everyone has done everything in a certain manner.

My main responsibilty was Kodi. I tried different approaches (see [Protocol - Kodi](../../Protocol/Protocol.md#kodi), what costs me a lot of time to find the right solution for this. After all, we can Pause and Play Kodi remotely. Party mode was on. ;-)

One of the main issues of the team was Snowboy. We wanted to set up voice commands with that, but there always occured some strange errors. We tried on different platforms (Mac, Windows, PI), but no luck for us, what was quite frustrating for us. Due to the lack of documentation, we had no idea how to face that issue. Because Bernhard had voice commands as the main responsibility, he tried to find another solution and found a working one (Adafruit with IFTTT). 

After the two days, nearly everything worked out as exptected. I finalized the presentation to be well prepared for the in class presentation and live demo.

### Project 3 - presentation and live demo
Bernhard had some issues with the voice command again, but he finally made it for the presentation. After that all things were set up correctly and the presentation with the live demo worked out very well.

Some notes about the other group presentations:
* ENI
   * Cool timing idea, going through the whole day in fast motion
   * Nice DYI smart water boiler
   * Good presentation
   
* ENI (Internationals)
   * Why no live demo?!
   * Lot of things they played around with and tried out
   * Not that related to their use cases

### Course reflection
Afer all, the course was quite different than the other ones in that degree program. We had do a lot of practical work, and on our one. I liked that very much because I think with the practical work and the hands on experience, you can learn more than just sitting in front of the video projector. 
Personally I would have liked to hear more about what happens behind the scenes, e.g. when we do some commands on the WEMOS, how to set something up (from the beginning), why using this technology and not this, etc. We worked an an rather high level of abstraction.
Another thing is that I do not really like the Matrix chat. Moodle also provides all the neccessary stuff for managing a course (discussion forum, deadlines) etc. This would be helpful because with Matrix I (and all the other MC-guys) often missed some chat details and/or deadlines. In moodle, we have a look at it every day.
