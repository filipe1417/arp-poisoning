# arp-poisoning

Python script for arp poisoning - using Scapy

# Requirements

To use this script, you'll need to install:
* Python 3.*
* Scapy 2.4.5

# Usage

This script can be used to perform ARP poisoning and its derivative attacks such as man in the middle, denial of service or session hijacking.

## IP Forwarding

To view packets that are not intended for you, you must enable IP Forwarding. Still, it is possible to use the script without activating it if your objective is to receive the packets and discard them, interrupting the communication between the two targets - in this case, if one of the targets is the gateway, the target will not be able to connect to the internet.

### Intercept packets and allow communication
For this, enable IP Forwarding.
Open the following file with your favorite text editor:
'/proc/sys/net/ipv4/ip_forward'

```
Eg. vim /proc/sys/net/ipv4/ip_forward
```
After that, set the value inside to 1

### Drop packets and interrupt communication
Disable IP Forwarding.
Open the following file with your favorite text editor:
'/proc/sys/net/ipv4/ip_forward'

```
Eg. vim /proc/sys/net/ipv4/ip_forward
```
After that, set the value inside to 0

## Examples

> sudo ./arpPoison.py 10.0.0.2 - arp poisoning between the host 10.0.0.2 and the gateway

> sudo ./arpPoison.py 10.0.0.2 10.0.0.3 - arp poisoning between the host 10.0.0.2 and 10.0.0.3

# Contributions
Contributions are very welcome. If you don't know where to start, look at the TODO list below, but you can add or remove what you want - just make a pull request. 

# TODO
* Better variable names
* The script must run as "sudo" - add a condition to remind users that when executing without "sudo"
* Use less scapy functions - more pure python
* README with wireshark examples
* Create a commented code - maybe using jupyter notebook or just a new script alongside the main one.

