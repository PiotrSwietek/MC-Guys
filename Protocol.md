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

we copied the system_template and renamed it to onboard_blinker.
Then we connected the ESP8266 and flashed it with the ulno software with the initialize command.
Now we could control the led through WIFI with the console command.
Now we can turn on the LED with the command onboardled onboardled.init(Pin.OUT)
And turn it off with onboardled.on
(The commands are inversed)


Then we created a new output port for simple led. The used name will be appended to MQTT topic and a set appended to send commands to.
Command: d("led", "blue", onboardled)

now we can turn off the led through MQTT with the command: mqtt_send_onboard_blinker/blue/set on


## IoT Nodes

Commands are faster than the provided filebrowser from MobaXTerm (for denis).

Misunderstanding with the config files system.conf and node.conf

d("led","blue",onboardled)

d("button", "switch", d1, "depressed", "pressed")

# 22.03.2018
