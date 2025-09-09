# Extra Topics in Cybersecurity

## TCP vs. UDP: A Detailed Comparison

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two of the most common transport layer protocols used in IP networks. They both provide a mechanism for sending data between applications on different hosts, but they do so in fundamentally different ways.

| Feature                  | TCP (Transmission Control Protocol)                                                                                             | UDP (User Datagram Protocol)                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Connection Model**     | **Connection-Oriented:** Establishes a reliable, end-to-end connection using a three-way handshake (SYN, SYN-ACK, ACK) before data transfer begins. The connection is terminated with a four-way handshake. | **Connectionless:** No prior connection is established. Datagrams are sent to the destination without any initial setup.         |
| **Reliability**          | **Reliable:** Guarantees that data will be delivered in the correct order and without errors. It uses sequence numbers to track packets and acknowledgments (ACKs) to confirm receipt. Lost packets are retransmitted. | **Unreliable:** Provides a "best-effort" delivery service. There is no guarantee of delivery, order, or duplicate protection. No acknowledgments are sent. |
| **Flow Control**         | **Yes:** Implements flow control using a sliding window mechanism. The receiver advertises its available buffer space (receive window), preventing the sender from overwhelming it. | **No:** Does not have a built-in flow control mechanism. Data is sent at the application's desired rate, which can lead to packet loss if the receiver cannot keep up. |
| **Congestion Control**   | **Yes:** Includes sophisticated congestion control algorithms (e.g., slow start, congestion avoidance) to prevent the network from becoming overloaded. It adjusts the sending rate based on network conditions. | **No:** Does not have a congestion control mechanism. Applications using UDP must implement their own if needed.                               |
| **Header Size**          | **20 bytes** (plus options, which can extend it up to 60 bytes). The larger header contains fields for sequence numbers, acknowledgments, window size, etc. | **8 bytes.** The smaller, fixed-size header contains only the essential information: source/destination ports, length, and checksum. |
| **Speed**                | **Slower:** The overhead of establishing a connection, ensuring reliability, and managing flow/congestion control makes TCP slower than UDP. | **Faster:** The lack of connection setup, acknowledgments, and other overhead makes UDP significantly faster and more efficient for certain applications. |
| **Use Cases**            | Applications requiring high reliability, where data integrity is paramount: Web browsing (HTTP/HTTPS), email (SMTP, POP3, IMAP), file transfer (FTP, SFTP), and secure shell (SSH). | Applications that are delay-sensitive and can tolerate some packet loss: Real-time streaming video and audio, online gaming, Voice over IP (VoIP), and DNS. |

## Address Resolution Protocols

In network communication, devices use different types of addresses at different layers of the OSI model. The Network Layer uses logical addresses (IP addresses), while the Data Link Layer uses physical addresses (MAC addresses). Address resolution protocols are essential for translating between these two types of addresses.

### Address Resolution Protocol (ARP)
ARP is a protocol used to discover the MAC address of a device from its known IP address. When a host wants to send a packet to another host on the same local network, it needs the destination host's MAC address to create the Data Link Layer frame.

**How ARP Works:**
1.  The sending host checks its ARP cache (a table of recently resolved IP-to-MAC address mappings).
2.  If the mapping is not in the cache, the sending host broadcasts an ARP Request packet to the entire local network. This packet contains the target host's IP address and asks, "Who has this IP address?"
3.  All hosts on the network receive the ARP Request, but only the host with the matching IP address will respond.
4.  The target host sends an ARP Reply packet directly to the original sender. This packet contains its MAC address.
5.  The original sender receives the ARP Reply, updates its ARP cache with the new mapping, and can now send the IP packet.

### Reverse Address Resolution Protocol (RARP)
RARP is an obsolete protocol that was used by a host to discover its own IP address when it only knew its MAC address. This was typically used by diskless workstations at boot time.

**How RARP Worked:**
1.  A host would broadcast a RARP request packet containing its own MAC address.
2.  A RARP server on the network, which maintained a table of MAC-to-IP address mappings, would receive the request.
3.  The RARP server would look up the MAC address in its table and send a RARP reply containing the corresponding IP address.

RARP had several limitations and has been largely replaced by more advanced protocols like BOOTP and DHCP.

### Dynamic Host Configuration Protocol (DHCP)
DHCP is the modern standard for automatically assigning IP addresses and other network configuration parameters to devices. It is a more robust and feature-rich protocol than RARP.

**How DHCP Works:**
1.  **Discover:** A client device broadcasts a DHCP Discover message to find a DHCP server.
2.  **Offer:** DHCP servers on the network respond with a DHCP Offer message, which contains a proposed IP address and other configuration information.
3.  **Request:** The client selects one of the offers and broadcasts a DHCP Request message to accept it.
4.  **Acknowledge:** The DHCP server that made the offer responds with a DHCP Acknowledge message, confirming the IP address lease.

## Advanced Cybersecurity Topics

### Intrusion Detection and Prevention Systems (IDPS)

An IDPS is a security tool that monitors network or system activities for malicious activity or policy violations.
-   **Intrusion Detection System (IDS):** An IDS is a passive system that monitors traffic and reports potential threats to a network administrator. It does not take any action to block the threat.
-   **Intrusion Prevention System (IPS):** An IPS is an active system that is placed in-line with the traffic flow. It can detect and block potential threats in real-time.

### Malware Analysis

Malware analysis is the process of dissecting malware to understand its functionality, origin, and potential impact. This can be done through:
-   **Static Analysis:** Examining the malware without executing it. This involves analyzing the code, strings, and other artifacts within the malware file.
-   **Dynamic Analysis:** Executing the malware in a controlled environment (a sandbox) to observe its behavior.

### Digital Forensics

Digital forensics is the process of collecting, preserving, analyzing, and presenting digital evidence in a manner that is legally admissible. It is a critical component of incident response and is used to investigate cybercrimes.

### Penetration Testing (Ethical Hacking)

Penetration testing is a simulated cyberattack against a computer system, network, or web application to find and exploit security vulnerabilities. The goal of a penetration test is to identify security weaknesses before a malicious actor does.

### Security Information and Event Management (SIEM)

A SIEM is a solution that provides real-time analysis of security alerts generated by network hardware and applications. It collects log data from various sources, identifies and categorizes incidents and events, and provides reports and alerts.