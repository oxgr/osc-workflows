# OSC Workflows
This document outlines different ways to connect devices using the Open Sound Control (OSC) protocol.

## Preparation
Before you get started, determine the proper context for this implementation. Ask questions such as:
- What devices need to be connected?
- Who is developing and/or maintaining this network?
- What is their preferred medium for programming? **Text-based or visual**?
- Do you prioritise **ease of setup or customisability**?

## Steps
### Connect devices
Make sure all devices are connected to the same network, either wirelessly or through an ethernet cable, **ideally to a single router**. Simplifying the network will save on possible networking drama.

### Set static IP addresses
When devices connect to a router, the router usually assigns them an [IP address](#ip-address) based on what open slots it has available. Think air traffic controllers assigning runways to airplanes. This process is known as DHCP.

However, the router can change IP addresses on a whim if it deems it necessary. Usually, this doesn't make much of a difference, but when dealing with OSC, we need all our devices to know exactly where to find each other. To do this, we set a **static IP address**, one that the router knows to never change.

### Find IP addresses
Open a terminal/command prompt and run the command for the associated operating system.

#### Linux
```shell
# If the device is only connected to one network
hostname -I 
```

#### macOS
```shell
# If connecting via wifi
ipconfig getifaddr en0 

# If connecting via ethernet
ipconfig getifaddr en1
```

### Set up OSC implentations


### Test

## Raspberry Pi
There are numerous ways to work with OSC on a Pi.
### [Node-RED](./pi-nodered.md)
- Pros
	- simple setup
	- built-in messaging protocols
	- easy to deal with GPIO data
	- editable from other devices in network
- Cons
	- not very maintained
	- a bit of a learning curve



## Alternatives
- MQTT
	- similar address/message structure
	- higher latency
	- lower message frequency
	- better energy efficiency
	- good for IoT devices running on battery power

## Glossary
### OSC
At its core, OSC is simply a protocol that determines how devices package, send, and receive data. 

- Messages are sent to devices using their IP address.
- Messages are further divided into OSC addresses. 
- Messages can be of different types (text, number) and the handling of types is usually determined by the implementation you choose for your device.

### IP address
A networking address that identifies devices in a local network. On Linux machines, this can usually be found by running `hostname -I` into a terminal. 

Example:
```
192.168.0.1
10.0.0.19
```
Numbers are separated by a period (`.`) and usually range from 0-255.

For simple networks, the **first three numbers determine the network** and is set by the router.

The **final number is unique** to each device connected to the network.