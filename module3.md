# MODULE 3: Network Layer

The Network Layer is the third layer of the OSI model. It is responsible for providing logical addressing, routing, and path determination for data packets. The Network Layer's primary function is to enable communication between devices on different networks, a process known as internetworking.

## Internetworking Devices

Internetworking devices are the building blocks of large-scale networks. They operate at different layers of the OSI model and perform distinct functions.

-   **Repeaters:** These are simple devices that operate at the Physical Layer. They regenerate the electrical signal to extend the distance a signal can travel over a particular medium. They do not perform any filtering or forwarding of data.
-   **Hubs:** Also operating at the Physical Layer, hubs are used to connect multiple devices in a star topology. A hub is essentially a multi-port repeater. Any data received on one port is broadcast to all other ports, which can lead to collisions and inefficient use of bandwidth.
-   **Bridges:** Bridges operate at the Data Link Layer. They are used to connect two or more LAN segments. Unlike hubs, bridges can filter traffic based on the MAC addresses of the connected devices. This helps to reduce unnecessary traffic on each segment.
-   **Switches:** A switch is a more advanced version of a bridge, also operating at the Data Link Layer. It has multiple ports and can forward data to a specific port based on the destination MAC address. This creates dedicated, collision-free paths between devices, significantly improving network performance.
-   **Routers:** Routers are the quintessential Network Layer devices. They are used to connect different networks and forward packets between them based on their IP addresses. Routers use routing tables to determine the best path for a packet to reach its destination.
-   **Gateways:** A gateway is a general term for a device that connects two networks that use different protocols. Gateways can operate at any layer of the OSI model and perform protocol conversion to allow communication between the disparate networks.

## IP Addressing and Subnetting

-   **IP Addressing:** An IP address is a unique numerical identifier assigned to each device on a network. It serves two main functions: identifying the host and its location on the network. The most common form of IP address is IPv4, which is a 32-bit address.
-   **Subnetting:** Subnetting is the process of dividing a large IP network into smaller, more manageable subnetworks, or subnets. This is done by "borrowing" bits from the host portion of the IP address to create a subnet identifier. Subnetting can improve network performance by reducing broadcast traffic and can also enhance security by isolating different parts of the network.

## Network Layer Protocols

### IPv4
Internet Protocol version 4 (IPv4) is the dominant protocol at the Network Layer. It provides a connectionless datagram service, meaning that each packet is treated independently, and there is no guarantee of delivery, order, or error-free transmission. An IPv4 address is a 32-bit number, which allows for approximately 4.3 billion unique addresses.

### IPv6
Internet Protocol version 6 (IPv6) is the successor to IPv4. It was developed to address the impending exhaustion of IPv4 addresses. IPv6 uses a 128-bit address, which provides a virtually limitless number of unique addresses. IPv6 also includes other improvements, such as simplified header formats, better support for security (IPsec), and more efficient routing.

### ICMP (Internet Control Message Protocol)
ICMP is a supporting protocol that is used by network devices to send error messages and operational information. For example, the popular "ping" utility uses ICMP to test the reachability of a host. ICMP messages are encapsulated within IP packets.

## Address Mapping

### ARP (Address Resolution Protocol)
ARP is used to map a known IP address to its corresponding MAC address. When a device needs to send a packet to another device on the same local network, it must know the destination device's MAC address. If the MAC address is not in the device's ARP cache, it will send out an ARP request broadcast to the entire network. The device with the matching IP address will respond with its MAC address.

### RARP (Reverse Address Resolution Protocol)
RARP is an obsolete protocol that was used by a device to discover its own IP address. It has been largely replaced by BOOTP and DHCP.

### DHCP (Dynamic Host Configuration Protocol)
DHCP is a network management protocol that is used to automatically assign IP addresses and other network configuration parameters to devices on a network. This simplifies network administration, as it eliminates the need for manual IP address configuration.

## Routing Algorithms

Routing algorithms are used by routers to determine the best path for a packet to travel from its source to its destination.

-   **Link-State Routing:** In a link-state routing protocol, each router builds a complete map of the network topology. This map is then used to calculate the shortest path to all other routers, typically using an algorithm like Dijkstra's. Link-state protocols converge quickly but can be more complex and resource-intensive than distance-vector protocols. OSPF (Open Shortest Path First) is a popular link-state routing protocol.
-   **Distance-Vector Routing:** In a distance-vector routing protocol, each router maintains a routing table that lists the "distance" (e.g., number of hops) to all known destinations. This information is periodically shared with the router's immediate neighbors. Distance-vector protocols are simpler than link-state protocols but can be prone to routing loops and slow convergence. RIP (Routing Information Protocol) is a classic example of a distance-vector protocol.