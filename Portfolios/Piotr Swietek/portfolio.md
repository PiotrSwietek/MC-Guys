# Introduction

My name is Piotr Swietek and I am studying Mobile Computing and I also did my Bachelors degree here in Hagenberg. I am studying mobile computing because I like developing for mobile devices.

I take this class because I am interested in this topic and would like to have an introduction to this field. And maybe I will automate my own home in the future.

I am probably more the programming type in a group. I can realize the ideas of others in form of code.

# Filmnotes

## Big bang theory
### Scenarios and domains
	turn lamp online
	turn stereo on
	remote cars
	public access

### Technologies
	laptop
	internet

### Feasable?
	yes doable
	
### weirdness
	the steering through internet is not crazy
	but public access is
	
## Smart buildings - Siemens

### Scenarios
	security
	flexibility
	efficiency
	comfort & health
	personal navigation
	lightning used for navigation

### Technologies
	standard interfaces
	plug and go

### Feasable
	yes could be doable but requires a lot of ressources to do

### weirdness
	not really
	
## Internet of Shrimps

### Scenarios
	use IoT for controlling kitchen tools
	own soda dispenser in the phone

### Technologies
	heavy modified smart phone

### Feasable
	not really - because why?

### weirdness
	very weird
	
# Setting up Raspberry Pi

We downloaded the image from ulnoiot and made sure that the checksum is the same as stated on the source site.
Then we flashed the SD card with it using Etcher.

We set the values in the config file to:
uiot_ap_name:		mc_guys_2
uiot_ap_password:	mcguys123

When entering the SD we thought the Pi is broken because we did not felt the spring when we inserted the card but the proffessor told us this Pi has no spring installed so all was fine.

Then we started the Pi and connected to it via the ssh agent (MobaXTerm). Then we changed the user password for pi from ulnoiot to mcguys123.
The next step is the updating of the ulnoiot software.
Then we expanded the harddisk in the raspi-config.

Now the raspberry is set up correctly and we can log into the created WiFi mc_guys2
In this exercise I learned how to set up a raspberry pi with a flashed SD card and how to configure it.

# IoT domains

Healthcare - Monitor hand hygiene compliance through IOT device and sensors to reduce transmission of Hospital Acquired Infections to patients.
Transport and logistics - Monitoring the logistics vehicles health to send alerts.
Retail - Remote interaction with products increase personalized shopping experience.
Insurance - Tracking clients' activity and offer discounts or rewards for healthy and safe behavior.
Farming - Tracking soil health and climate.

## Devices:
* smart locks
* smart plugs
* smart lighting
* smart thermostats

# Node onboard_blinker

we copied the system_template and renamed it to onboard_blinker.
Then we connected the ESP8266 and flashed it with the ulno software with the initialize command.
Now we could control the led through WIFI with the console command
It should be noted that the device needs about a minute to boot and set up. So you cant connect to the device in this time. This happened to us many of times and caused confusion.
Now we can turn on the LED with the command onboardled onboardled.init(Pin.OUT)
And turn it off with onboardled.on()

It was confusing at first because the commands were inversed.

Then we created a new output port/device for simple led. The used name will be appended to MQTT topic and a set appended to send commands to.
Command: d("led", "blue", onboardled, "off", "on").
After that we have to use the run() command to publish the device and make them accessible through the network.

now we can turn on the led through MQTT with the command: mqtt_send onboard_blinker/blue/set on
In this exercise I learned how to use the ESP8266. I have never worked with it before and it is remarkable how much you can do with such a small device.
Also I used MQTT the first time and I like it so far.

# H&B Automation Term - what is it used for

* Make life easier / convenience
* Security
* Energy efficiency
* Lighting
* Heating
* Indoor positioning
* Safety (fire & waterdamage)

# MQTT - NodeRed

Task was to steer the blinker through a button. But both were on seperate devices only communicating through the WiFi.
We followed the solution of Bernhard Hiesl & Denis Sivak //Link here

The MQTT commands caused us trouble because we forgot that we had to use them on the pi and not in the device console.
Also we forgot to execute the run() command so all the MQTT set requests would not be executed.

We also edited the autostart.py file of the devices so we didnt had to define the devices every time we connected it to the power.
First we always flashed the device when editing the autostart.py to copy it onto the device but then we realised we could use the deploy command to copy it.

In this exercise I learned what NodeRed is and it looks like a very nice and convenient tool to define network processes. Also it was fascinating when it all worked.
We had some trouble setting it all up but in retrospective it isnt hard at all.

# Smart Lock

Task was to control a magnetic lock through a graphical UI in the web using NodeRed.

The lock would be steered through a relay(electrical switch). We connected one connector of the lock to the powersupply and the other to the relay.
The relay was connected to the powersupply of the lock and the lock itself. Now we have to define a new device for the output port:
d("out","output",d2);

Now when we run the command output.evaluate() and the lock locks/unlocks which is pretty awesome.