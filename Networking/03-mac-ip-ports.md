# 03 MAC, IP and Ports

## MAC

- A MAC address is a unique identifier physically written into the hardware (NIC). It operates at OSI Layer 2.

- We use MAC addresses to forward packets within a Local Area Network (LAN). When our information leaves the local network, the MAC address changes in each hop.

- The MAC address is like a unique apartment number in a building.

- A MAC address is made up of 48 bits in the format AA:AA:AA:AA:AA:AA. The first half (AA:AA:AA) is call the OUI (Organizationally Unique Identifier), it identifies the company that manufactured the Network Card Interface (NIC). The second half identifies the specific NIC itself. This is why exposing a full MAC address can reveal information about our hardware.

## IP

- An IP is a logical address assigned to a device so it can communicate between networks.

- The IP address is like the building we want to reach.

- An IPv4 address is made up of 32 bits in the format 192.168.0.1. We use private addresses within our local network, and public addresses to communicate to the internet and other networks.

- As billions of devices connected to the internet, we almost used up the available IPv4 addresses. That is why IPv6 was introduced, it provides practically unlimited address space.

## Ports

- A device runs many applications at the same time, so how does it know which application should receive the information. That is why we need ports, it tells the OS which application to send the data.

- Ports are like the specific rooms inside our apartment.

- There are 65,535 ports available we can use, although some of them are reserved for specific purposes.

- Port 22 for SSH, Port 443 for HTTPS and Port 80 for HTTP...

## How does a packet travel across networks to reach a specific service?

### Layer 2 - Data Link

- First, our traffic moves within the local network using MAC addresses: our device sends the packet to our router using the router's MAC address.

### Layer 3 - Network

- Then, the router uses IP addresses to forward the packet to the destination network, hopping between routers until it reaches the destination device.

### Layer 4 - Transport

- Once the packet arrives at the destination device, the OS reads the port number to determine which application or service should receive the data.
