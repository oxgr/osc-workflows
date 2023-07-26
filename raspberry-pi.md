# Raspberry Pi
There are numerous ways to work with OSC on a Pi. If interested in a more visual programming method, try out Node-RED. If you prefer a traditional text-based method, consider Python or Javascript.

## Node-RED
Node-RED is a visual programming framework that lets you do a lot of what you can do in code, but with a friendlier node/network-based interface. 

- Pros
	- simple setup
	- built-in messaging protocols
	- easy to deal with GPIO data
	- editable from other devices in network
- Cons
	- not very maintained
	- a bit of a learning curve

### Setup
Follow instructions [here](https://nodered.org/docs/getting-started/raspberrypi). You would ideally run Node-RED **as a service** or have it **autostart on boot**.

To edit the network, open a browser on the Pi or another device connected to the same network and navigate to `http://<ipaddress>:1880`, where `<ipaddress>` with the Pi's IP address found [here](README.md#3.-find-ip-addresses).

### Send 