# Accessing the device over network


Once hardware (sensors, cameras, etc.) are set up, it is easier to work on your dev machine (laptop/desktop). This lets you debug you app on the go without attaching the board to a monitor.

There are multiple ways to connect to the device over the network. This doc will discuss the methods I used while fiddling with Jetson ORIN.


## `ssh` on local network
For the most part, my dev laptop and the board are on same network. `ssh` was good enough for this situation. 


### Setting up SSH keys for remote access

* Generate SSH keys, if not present already.
* Find IP address of the board
* SSH using username and password
* Copy your public key on to the board 

### HostName based access 
It is highly likely that your device has a dynamic IP address allocated to it. We could go the route of statically configuring an IP address on the router. It will get tedious when we start adding more devices.

To access the device with hostname, there are three ways:
1. Setup and run a local DNS server. We could do this, but it is an overkill for just a few devices
2. Run `mDNS` to broadcast hostname requests. The device is accessible only on the local network
3. Use `tailscale` to set up a mesh based VPN to access your devices across the world. Since the devices access is through a VPN, they do not need to be on the same network.


Options 2 or 3 are the easiest to setup and the choice really depends on you access needs. If you want to be able to access your devices while you are away, Tailscale is a better option.

#### mDNS setup


#### Tailscale setup



