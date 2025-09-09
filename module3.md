# MODULE 3: Network Layer

## Internetworking Devices
Internetworking devices are used to connect different networks together. Some common devices include:
-   **Repeaters:** Operate at the physical layer and regenerate the signal to extend the distance over which a signal can travel.
-   **Hubs:** Also operate at the physical layer and are used to connect multiple devices in a network. A hub broadcasts all data to all connected devices.
-   **Bridges:** Operate at the data link layer and are used to connect two LANs. They can filter traffic based on MAC addresses.
-   **Switches:** A more advanced version of a bridge, a switch operates at the data link layer and can forward data to a specific port based on the MAC address.
-   **Routers:** Operate at the network layer and are used to connect different networks. They use IP addresses to forward packets to their destination.
-   **Gateways:** Can operate at all seven layers of the OSI model and are used to connect networks that use different protocols.

## IP Addressing and Subnetting
-   **IP Addressing:** An IP address is a unique numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.
-   **Subnetting:** Subnetting is the process of dividing a large network into smaller, more manageable subnetworks, or subnets. This can improve network performance and security.

## Network Layer Protocols
### IPv4
Internet Protocol version 4 (IPv4) is the fourth version of the Internet Protocol (IP). It is one of the core protocols of standards-based internetworking methods in the Internet and other packet-switched networks. It uses a 32-bit address space.

### IPv6
Internet Protocol version 6 (IPv6) is the most recent version of the Internet Protocol (IP). It is the successor to IPv4 and is designed to solve the problem of IPv4 address exhaustion. It uses a 128-bit address space.

### ICMP (Internet Control Message Protocol)
ICMP is a supporting protocol in the Internet protocol suite. It is used by network devices, like routers, to send error messages and operational information indicating, for example, that a requested service is not available or that a host or router could not be reached.

## Address Mapping
### ARP (Address Resolution Protocol)
ARP is a communication protocol used for discovering the link layer address, such as a MAC address, associated with a given internet layer address, typically an IPv4 address.

### RARP (Reverse Address Resolution Protocol)
RARP is a protocol by which a physical machine in a local area network can request its IP address from a gateway server's address resolution protocol table or cache.

### DHCP (Dynamic Host Configuration Protocol)
DHCP is a network management protocol used on Internet Protocol (IP) networks for automatically assigning IP addresses and other communication parameters to devices connected to the network.

## Routing Algorithms
Routing algorithms are used by routers to determine the best path for a packet to travel from its source to its destination.
-   **Link-State Routing:** Each router builds a map of the entire network in the form of a graph. The router then uses this map to calculate the shortest path to all other routers.
-   **Distance-Vector Routing:** Each router shares its routing table with its immediate neighbors. The routers then use this information to update their own routing tables and determine the best path to a destination.