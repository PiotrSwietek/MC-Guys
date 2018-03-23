# 19.03.2018
## Project setup
* Set up project team (Codename: MC-Guys)
* Set up git repo on GitHub with all access rights for members
	* Every team member has own folder with its own portfolio
	* Providing a central protocol as a technical documentation
	* The portfolio of each member gives a personal insight of the tasks done in the lecture

## UlnoIoT environment setup
### Raspberry
* WFollowing the tutorial on https://github.com/ulno/ulnoiot#installation
* Download pi image from repo
* Flash SD-Card with Etcher (https://etcher.io/)
* On file system, check config file and change Wifi-SSD and password for each Pi
	* pattern: SSID: mc_guys_[nr], password: mcguys***
* Boot raspberry
* Connect to configured Wifi
* Connect to Pi via SSH agent (Windows: MobaXTerm (https://mobaxterm.mobatek.net/), Mac/Linux: Console) via *ssh -x pi@[ip]*
* Change password: Same as Wifi password
* Update UlnoIoT framework via *ulnoiot upgrade*
* Expand harddisk via *raspi-config*


### IoT nodes
* Following the tutorial on https://github.com/ulno/ulnoiot#first-iot-nodes
* After initialization, plug in to other computer, wait for bootup (30s)
* On Pi, connect to node via *console*
* Testing onboard led locally
	*onboardled.init( Pin.OUT )
	*onboardled.on()
	*onboardled.off()
	*onboardled.on()

* Turn on/off onboard led via MQTT
	* define a device via *d("led","blue",onboardled, "on", "off")*. This also defines a MQTT-topic which the node continuously listens to. Topic name: *[node_name]/[devicename]/set 
	* running node via *run()*
	* Test MQTT-sending on the Pi (not in console) via *mqtt_send *[node_name]/[devicename]/set [on/off]

# 22.03.2018
## UlnoIoT Hello World
Trigger a led of one node with a button press of another one.
* create a new node on Pi 
* flash on node
* connect to it and define button: d("button", "button1", d1, "on", "off"), continuously publishing to MQTT-topic  
* Run node via *run()*
* MQTT-forwarding mechanism on Pi, e.g. *mqtt_action button_blinker/button1 anychange [some-name] mqqt_send onbard_blinker/blue/set*
* Button press now triggers led
* To enable plug&play, we have to setup some configuration in the *autostart* file. To find in the node folder on the Pi.
	* Writing commands for defining devide (d-command) and run-command inside file.
	* Deploy autostart file to node via *deploy* in node folder


## Relay
Trigger a lock (12V) with a relay controlled by a button.
* Button already set up
* Wiring up relay with lock, relay needs 12V (not sure, using separate power adpater) and plug in in relay with node
* register device relay *d("out", "relay", d2)*
* testing locally *device["relay].evaluate["on"]*
* testing MQTT on Pi *mqtt_send relay/set on*

# 23.03.2018
## Control servo/lock vai a RFID-reader
* Create and flash new node
* Wire up RFID following instructions on (https://github.com/ulno/ulnoiot/blob/f64b72f320a11c42b93f8c53222fdaaf404fe221/doc/wiring-mfrc522.txt)
* Create device via *r=d("mfrc522","r",d0)*
* Write data to a mifare classic card *r.write("hello from hagenberg")*, continously publishing on MQTT-topic, e.g. [node-name]/[devicename]
* Run node *run()*
* Because the RFID tag delivers an ID and we want to check for the "right" card, we must need some logic to filter out MQTT-Messages. Using Node-RED (https://nodered.org/)
* Node-Red is already installed on the Pi, connect to it (http://192.168.12.1:1880/)
* Create a new Flow filtering out the ID, and manipulate message payload to on/off.





# (old) notices

Commands are faster than the provided filebrowser from MobaXTerm (for denis).

Misunderstanding with the config files system.conf and node.conf


d("button", "switch", d1, "depressed", "pressed")

## Configure Node1 and Node2
The biggest problem this morning was, that we couldn't figure out which device is node 1 and node 2. Therefore we write it down

node1 = LED
node2 = BUTTON

We had some weird problems with the connection to the nodes. looked like an network error. after updating the autostart and flash both devices everything was up and running. the restart of the node1 after plug it into my pc it tooks a little bit longer than 10-15s but all in all everything is now working. and we can continue with our exercise

## Node RED
Programming tool for wiring together hardware devices.

Everything was clear except the automatically intizialization of the local variable context.togglestate.


### Piotr, Manuel, Oliver
- invite manuel, denis and bernhard to ulnoiot and ulnoiot.mc0509 to riot via email




