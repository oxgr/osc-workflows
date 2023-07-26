# OSC Workflows
This document outlines different ways to connect devices using the Open Sound Control (OSC) protocol.
## Preparation
Before you get started, determine the proper context for this implementation. Ask questions such as:
- What devices need to be connected?
- Who is developing and/or maintaining this network?
- What is their preferred medium for programming? **Text-based or visual**?
- Do you prioritise **ease of setup or customisability**?

## Steps
1. Connect all devices to the same network.
2. Find the IP addresses of each device to send/receive from.
3. Set up OSC implentations for each device.
4. Test devices in isolation.
5. Test devices together.

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