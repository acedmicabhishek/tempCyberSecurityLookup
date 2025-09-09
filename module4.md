# MODULE 4: Transport Layer

## Process-to-Process Delivery
The transport layer is responsible for process-to-process delivery, which means it delivers data not just from one computer to another, but from a specific process on one computer to a specific process on another.

### UDP (User Datagram Protocol)
UDP is a connectionless, unreliable transport protocol. It provides a very simple interface between the network layer and the application layer.
-   **Connectionless:** No connection is established before sending data.
-   **Unreliable:** It does not guarantee delivery, order of delivery, or duplicate protection.
-   **Use Cases:** UDP is suitable for applications that can tolerate some data loss, such as streaming media, online gaming, and VoIP.

### TCP (Transmission Control Protocol)
TCP is a connection-oriented, reliable transport protocol. It provides a reliable, ordered, and error-checked delivery of a stream of octets between applications running on hosts communicating over an IP network.
-   **Connection-Oriented:** A connection must be established before data can be sent. This is done through a three-way handshake.
-   **Reliable:** TCP guarantees that data will be delivered to the destination in the same order it was sent. It uses sequence numbers and acknowledgments to ensure reliability.
-   **Flow Control:** TCP uses a sliding window protocol for flow control to avoid overwhelming the receiver.
-   **Use Cases:** TCP is used for applications that require reliable data transfer, such as web browsing, email, and file transfer.

## Congestion Control
Congestion in a network occurs when the load on the network is greater than the capacity of the network. Congestion control refers to the mechanisms used to control congestion and keep the network stable. TCP uses several algorithms for congestion control, including slow start, congestion avoidance, and fast retransmit/fast recovery.

## Quality of Service (QoS)
QoS refers to the ability of a network to provide better service to selected network traffic over various technologies. QoS is a way to manage network resources to provide a certain level of performance to an application. Some QoS parameters include:
-   **Bandwidth:** The rate at which data can be transferred.
-   **Latency (Delay):** The time it takes for a packet to travel from its source to its destination.
-   **Jitter:** The variation in the delay of received packets.
-   **Packet Loss:** The percentage of packets that are lost during transmission.