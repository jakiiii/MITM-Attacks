# Network Basics

- A network is a number of devices connecte together.
- Use: to transfer data or share resources between the connected devices.
- All networks (wifi or wried) achieve this using the smae principle.
- One device acts as a server, the server contains the data that is shared between the connected devices.
- Most wifi networks, the server is the router.
- THe only devices in the network that has access to the shared data is the server.
- All the connected deviece of the network have no direct access to the internet.


**MAC Address:**

- Each network card has a *physical static* address assigned by the card manufacturer called MAC (Media Access Control) address.
- This address is used between devices to identify each other and to transfer packets to the right place.
- Each packet has a source MAC and a desgination MAC.


# Information Gathering

- We will use **airodump-ng** to discover all the AP's arounds us and the clients associated.
- We connected to a specific AP, we can gather more detailsed info about the clients connected to this AP.

 
**Netdiscover**

Netdiscover is a program that can be used to discover the connected clients to out current network, its very quickly response but it does not show detailed information about the clients: IP, MAC address and some times the hardware manugacturer for the clients's wireless card.

```
netdiscover -i [INTERFACE] -r [RANGE]
ex: netdiscover -i wlan0 -r 192.168.1.1/24
```

**Autoscan**

Autoscan is another program that can be used to discover the connected clients to our courrent network, its not as quick as net discover, but it shows more detailed information about the connected devices and it has a graphical user inferface.

AutoScan Download: `sourceforge.net/projects/autoscan/files/AutoScan`

For use autoscan tool we need to 32bit architecture.

```
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6:i386
```

Then we need to update our os and then install autoscan tool.

```
/root/Downloads
bash autoscan-network-1.42-Linux-x86-Install
./autoscan-network-1.42-Linux-x86-Install
```

Now we can run autoscan tool.

**Nmap (Network Mapper)**

- Nmap is a network disocvery tool that can be used to gather detailed information about any client or network.
- Uses to discover connected clients and gather information about them.
- Zenmap - the GUI for Namp.
	1. *Ping Scan:* Very quick - only shows connected clients.
	2. *Quick Scan Plus:* Quick - shows MAC and open ports.
	3. *Quick scan plus:* Slower then the 2 above, more detailed info.