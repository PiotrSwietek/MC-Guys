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
