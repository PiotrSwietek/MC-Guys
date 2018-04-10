# 19.03.2018
## Setup raspberry pi
We went through the given tutorial.
Tutorial: https://github.com/ulno/ulnoiot

Short summary what we did:

We download the image from ulnoiot and made sure that the checksum is the same as stated on the source site.
Then we flashed the SD card with it using Etcher.

We set the values in the config file to:
uiot_ap_name:		mc_guys_2
uiot_ap_password:	mcguys123

When entering the SD we thought the Pi is broken because we did not felt the spring when we inserted the card but the proffessor told us this Pi has no spring installed so all was fine.

Then we started the Pi and connected to it via the ssh agent (MobaXTerm). Then we changed the user password for pi from ulnoiot to mcguys123.
The next step is the updating of the unloiot software.
Then we expaned the harddisk in the raspi-config.


## IoT Nodes

Commands are faster than the provided filebrowser from MobaXTerm (for denis).

Misunderstanding with the config files system.conf and node.conf

d("led","led1",onboardled)

d("button", "switch", d1, "depressed", "pressed")

# 22.03.2018
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
- flashing blinkder node for testing

- flashing blinker node
- plug in to other computer
- wait (e.g. 1 minute) to boot up
- connect via ssh to pi
- use "console" to connect to blinker
- testing local blinks via:
onboardled.init( Pin.OUT )
onboardled.on()
onboardled.off()
onboardled.on()

- testing blinker over mqtt
"console" in right node-folder:
d("led", "blue", onboardled, "on", "off")
on raspberry:
test mqtt messaging: mqtt_send_onboard_blinker/blue/set on

- settinup blinker on manuels raspberry
Make a folder iot-[yourname]
Copy the contents of ulnoiot/lib/system_template into your iot-folder
Rename node_template into onboard_blinker.
go to folder
plugin wemos d1 mini on raspberry usb
initialize to flash
plugin other computer
raspberry - go folder to node, command: console

-setting up button on raspberyy console for button_blinker
d("button", "button1", d1, "off", "on")
run()
testing with button press
on console: publishing button....


-forwarding actoin from button to blinker via mqtt
raspberry:
mqtt_action button_blinkder/button1 anychange xyz mqqt_send onbard_blinker/blue/set

-autostart file of each node folder
adding d commands to autostart file (at the end) to enable plug and play functionality
adding run commands

-autostart file deploying
folder of node
command: deploy

-node-RED
testing node-RED with the tutorial video

-lock with relay
wiring up relay with lock, relay needs 12V (using Pi power adpater) and plugin in relay with node
register device relay
d("out", "relay", d2)
test device
device["releay].evaluate["on"]
testing
mqtt_send relay/set on
