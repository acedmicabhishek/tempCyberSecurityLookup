# MODULE 4: Transport Layer

The Transport Layer is the fourth layer of the OSI model. It provides end-to-end communication services for applications. This layer is responsible for logical communication between processes running on different hosts. It takes data from the Application Layer, segments it into smaller units if necessary, and passes it to the Network Layer. It also ensures that the data is reassembled correctly at the destination.

## Process-to-Process Delivery

While the Network Layer is responsible for host-to-host delivery, the Transport Layer is responsible for process-to-process delivery. A process is an application program running on a host. The Transport Layer uses port numbers to identify the specific process to which data should be delivered. A port number is a 16-bit number that is used to identify a specific application.

### UDP (User Datagram Protocol)

UDP is a simple, connectionless transport protocol. It provides a "best-effort" datagram service, meaning that it does not guarantee delivery, order of delivery, or duplicate protection.

-   **Connectionless:** UDP does not establish a connection before sending data. Each datagram is treated as an independent unit.
-   **Unreliable:** UDP does not use acknowledgments or retransmissions to ensure that data is delivered. If a datagram is lost, it is not retransmitted.
-   **Minimal Overhead:** The UDP header is very small (8 bytes), which makes it efficient for applications that are sensitive to delay.
-   **Use Cases:** UDP is suitable for applications that can tolerate some data loss, such as real-time applications like streaming media, online gaming, and Voice over IP (VoIP).

### TCP (Transmission Control Protocol)

TCP is a connection-oriented, reliable transport protocol. It is the most widely used transport protocol on the Internet.

-   **Connection-Oriented:** Before any data is sent, TCP establishes a connection between the sender and receiver using a three-way handshake. This ensures that both sides are ready to communicate.
-   **Reliable:** TCP provides reliable data transfer by using sequence numbers, acknowledgments, and retransmissions. Each byte of data is assigned a sequence number. The receiver sends acknowledgments to confirm that it has received the data. If an acknowledgment is not received within a certain time, the sender retransmits the data.
-   **Flow Control:** TCP uses a sliding window protocol for flow control. This prevents the sender from overwhelming the receiver with too much data. The receiver advertises a "window size," which indicates how much data it is able to receive.
-   **Congestion Control:** TCP includes mechanisms to control congestion in the network. If the network becomes congested, TCP will reduce its transmission rate to avoid further congestion.
-   **Use Cases:** TCP is used for applications that require reliable data transfer, such as web browsing (HTTP), email (SMTP, POP3), and file transfer (FTP).

## Congestion Control

Congestion in a network occurs when the demand for resources (e.g., bandwidth, router buffers) exceeds the available capacity. This can lead to packet loss, increased delay, and reduced throughput. Congestion control refers to the mechanisms used to prevent and mitigate congestion. TCP uses several algorithms for congestion control:

-   **Slow Start:** When a new connection is established, TCP starts by sending a small amount of data and then exponentially increases the amount of data it sends until it detects congestion.
-   **Congestion Avoidance:** Once the congestion window reaches a certain threshold, TCP enters the congestion avoidance phase, where it increases the window size linearly.
-   **Fast Retransmit and Fast Recovery:** These are mechanisms that allow TCP to detect and recover from packet loss more quickly than waiting for a timeout.

## Quality of Service (QoS)

QoS refers to the ability of a network to provide a certain level of performance to an application. Different applications have different QoS requirements. For example, a real-time video application requires low latency and jitter, while a file transfer application is more concerned with throughput. QoS can be implemented at various layers of the network stack. At the Transport Layer, QoS can be managed by choosing the appropriate transport protocol (TCP or UDP) and by using mechanisms like traffic shaping and policing. Some key QoS parameters include:

-   **Bandwidth:** The data rate, measured in bits per second.
-   **Latency (Delay):** The time it takes for a packet to travel from its source to its destination.
-   **Jitter:** The variation in the delay of received packets.
-   **Packet Loss:** The percentage of packets that are lost during transmission.