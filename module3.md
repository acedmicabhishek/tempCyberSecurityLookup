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

#### IPv4 Header
The IPv4 header is the metadata at the beginning of an IP packet. It contains information that is essential for routing and delivery. The header is 20 bytes in length (without options) and consists of the following fields:

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |Version|  IHL  |Type of Service|          Total Length         |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |         Identification        |Flags|      Fragment Offset    |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |  Time to Live |    Protocol   |         Header Checksum       |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                       Source Address                          |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                    Destination Address                        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                    Options                    |    Padding    |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

-   **Version (4 bits):** Indicates the IP version (always 4 for IPv4).
-   **Internet Header Length (IHL) (4 bits):** The length of the header in 32-bit words.
-   **Type of Service (ToS) (8 bits):** Specifies the priority of the packet.
-   **Total Length (16 bits):** The total length of the packet (header + data) in bytes.
-   **Identification (16 bits):** Used for fragmentation and reassembly.
-   **Flags (3 bits):** Control flags for fragmentation.
-   **Fragment Offset (13 bits):** The offset of the fragment in the original datagram.
-   **Time to Live (TTL) (8 bits):** A counter that is decremented by each router. When it reaches zero, the packet is discarded. This prevents packets from looping indefinitely.
-   **Protocol (8 bits):** The transport layer protocol to which the data should be passed (e.g., TCP is 6, UDP is 17).
-   **Header Checksum (16 bits):** A checksum for error detection in the header.
-   **Source IP Address (32 bits):** The IP address of the sender.
-   **Destination IP Address (32 bits):** The IP address of the receiver.
-   **Options (variable length):** Optional fields that can be used for various purposes, such as security or source routing.

### IPv6
Internet Protocol version 6 (IPv6) is the successor to IPv4. It was developed to address the impending exhaustion of IPv4 addresses. IPv6 uses a 128-bit address, which provides a virtually limitless number of unique addresses. IPv6 also includes other improvements, such as simplified header formats, better support for security (IPsec), and more efficient routing.

#### IPv6 Header
The IPv6 header is 40 bytes in length and has a simpler structure than the IPv4 header.

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |Version| Traffic Class |           Flow Label                  |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |         Payload Length        |  Next Header  |   Hop Limit   |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                                                               |
   +                                                               +
   |                                                               |
   +                         Source Address                        +
   |                                                               |
   +                                                               +
   |                                                               |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                                                               |
   +                                                               +
   |                                                               |
   +                      Destination Address                      +
   |                                                               |
   +                                                               +
   |                                                               |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

-   **Version (4 bits):** Indicates the IP version (always 6 for IPv6).
-   **Traffic Class (8 bits):** Similar to the ToS field in IPv4.
-   **Flow Label (20 bits):** Used to identify packets that belong to the same flow.
-   **Payload Length (16 bits):** The length of the payload (data) in bytes.
-   **Next Header (8 bits):** Identifies the type of header immediately following the IPv6 header.
-   **Hop Limit (8 bits):** Similar to the TTL field in IPv4.
-   **Source Address (128 bits):** The IP address of the sender.
-   **Destination Address (128 bits):** The IP address of the receiver.

## Address Mapping

### ARP (Address Resolution Protocol)
ARP is used to map a known IP address to its corresponding MAC address. When a device needs to send a packet to another device on the same local network, it must know the destination device's MAC address. If the MAC address is not in the device's ARP cache, it will send out an ARP request broadcast to the entire network. The device with the matching IP address will respond with its MAC address.

### RARP (Reverse Address Resolution Protocol)
RARP is an obsolete protocol that was used by a device to discover its own IP address. It has been largely replaced by BOOTP and DHCP.

### DHCP (Dynamic Host Configuration Protocol)
DHCP is a network management protocol that is used to automatically assign IP addresses and other network configuration parameters to devices on a network. This simplifies network administration, as it eliminates the need for manual IP address configuration.

## Routing Algorithms and Routing Table Construction

Routing algorithms are used by routers to determine the best path for a packet to travel from its source to its destination. The output of these algorithms is a routing table.

### Routing Table Construction
A routing table is a data structure that is stored in a router or a networked computer that lists the routes to particular network destinations. There are two main methods for constructing a routing table:

-   **Static Routing:** In static routing, the routes are manually configured by a network administrator. This is a simple and secure method, but it is not scalable and does not adapt to changes in the network topology.
-   **Dynamic Routing:** In dynamic routing, routers use routing protocols to automatically learn about the network topology and build their routing tables. This is a more scalable and flexible method, as it can automatically adapt to network changes.

### Routing Algorithms
-   **Link-State Routing:** In a link-state routing protocol, each router builds a complete map of the network topology. This map is then used to calculate the shortest path to all other routers, typically using an algorithm like Dijkstra's. Link-state protocols converge quickly but can be more complex and resource-intensive than distance-vector protocols. OSPF (Open Shortest Path First) is a popular link-state routing protocol.
-   **Distance-Vector Routing:** In a distance-vector routing protocol, each router maintains a routing table that lists the "distance" (e.g., number of hops) to all known destinations. This information is periodically shared with the router's immediate neighbors. Distance-vector protocols are simpler than link-state protocols but can be prone to routing loops and slow convergence. RIP (Routing Information Protocol) is a classic example of a distance-vector protocol.