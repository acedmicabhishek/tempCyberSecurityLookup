# MODULE 2: Data Link Layer

The Data Link Layer (DLL) is the second layer of the OSI model and is responsible for providing reliable, node-to-node data transfer. It takes the packets from the Network Layer and encapsulates them into frames for transmission. The DLL is also responsible for flow control, error control, and managing access to the physical medium.

## Flow Control and Error Control Protocols

Flow control mechanisms are used to prevent a fast sender from overwhelming a slow receiver. Error control mechanisms are used to detect and retransmit damaged or lost frames.

### Stop-and-Wait ARQ
Stop-and-Wait Automatic Repeat Request (ARQ) is the simplest flow and error control protocol. The sender transmits a single frame and then waits for an acknowledgment (ACK) from the receiver. If the ACK is received within a specified timeout period, the sender transmits the next frame. If the ACK is not received, or a negative acknowledgment (NAK) is received, the sender retransmits the original frame. This protocol is inefficient due to the significant amount of time the sender spends waiting for acknowledgments.

### Go-Back-N ARQ
Go-Back-N ARQ improves efficiency by allowing the sender to transmit up to N frames without waiting for an ACK. The sender maintains a "sending window" of up to N frames. If the receiver detects an error in a frame, it sends a NAK for that frame. The sender then retransmits the erroneous frame and all subsequent frames that were sent after it. This is simpler to implement than Selective Repeat, but can be inefficient if the error rate is high, as it leads to the retransmission of many error-free frames.

### Selective Repeat ARQ
Selective Repeat ARQ is a more sophisticated protocol that allows the sender to transmit up to N frames without waiting for an ACK. However, unlike Go-Back-N, the receiver can accept and buffer frames that arrive out of order. If a frame is lost or damaged, the receiver sends a NAK for only that specific frame. The sender then retransmits only the lost or damaged frame. This is more efficient than Go-Back-N, especially on noisy links, but it requires more complex logic at the receiver to manage the out-of-order frames.

### Sliding Window
The sliding window is the underlying concept for both Go-Back-N and Selective Repeat ARQ. It is a theoretical model that allows for a continuous flow of data by enabling the sender to transmit a certain number of frames before receiving an ACK. The "window" of frames that the sender is allowed to transmit "slides" forward as ACKs are received.

## Multiple Access Protocols

In networks where multiple devices share a common communication channel, multiple access protocols are needed to coordinate access and avoid collisions.

### Pure ALOHA
Pure ALOHA is a simple protocol where a station can transmit a frame at any time. If a collision occurs (i.e., two or more stations transmit simultaneously), the frames are corrupted. The stations then wait for a random amount of time before attempting to retransmit. The simplicity of Pure ALOHA comes at the cost of low channel utilization, with a maximum theoretical efficiency of about 18.4%.

### Slotted ALOHA
Slotted ALOHA improves upon Pure ALOHA by dividing time into discrete slots. A station can only begin transmitting at the beginning of a time slot. This reduces the vulnerable period for collisions by half, and as a result, the maximum theoretical efficiency is doubled to about 36.8%.

### CSMA/CD (Carrier Sense Multiple Access with Collision Detection)
CSMA/CD is a protocol used in wired Ethernet networks. Before transmitting, a station "listens" to the channel to see if it is idle (carrier sense). If the channel is idle, the station begins transmitting. While transmitting, the station continues to listen for collisions (collision detection). If a collision is detected, the station immediately stops transmitting, sends a jam signal to notify other stations of the collision, and then waits for a random amount of time before attempting to retransmit.

### CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)
CSMA/CA is used in wireless networks (IEEE 802.11). In wireless environments, it is difficult to detect collisions while transmitting (the "near/far" problem). Therefore, CSMA/CA focuses on avoiding collisions in the first place. Before transmitting, a station can send a short Request to Send (RTS) message. If the receiver is ready, it responds with a Clear to Send (CTS) message. All other stations that hear the RTS or CTS will refrain from transmitting for the duration of the data transmission.

## Error Detection and Error Correction

These techniques are used to ensure the integrity of data during transmission.

### Fundamentals
-   **Error Detection:** The goal of error detection is to determine if a received frame contains errors. This is typically done by adding redundant information to the frame.
-   **Error Correction:** The goal of error correction is to not only detect errors but also to correct them at the receiver, without the need for retransmission. This requires more redundant information than error detection.

### Block Coding
In block coding, the message is divided into blocks of k bits, and r redundant bits are added to each block to create a codeword of n = k + r bits. The design of the block code determines its error detection and correction capabilities.

### CRC (Cyclic Redundancy Check)
CRC is a powerful error detection technique. It treats the bit stream as a polynomial and divides it by a predetermined generator polynomial. The remainder of this division is the CRC checksum, which is appended to the message. The receiver performs the same division. If the remainder is zero, the frame is considered error-free.

### Hamming Code
Hamming code is a family of linear error-correcting codes. It can detect up to two-bit errors or correct single-bit errors. Hamming codes are a type of block code and are widely used in computer memory and other applications where single-bit errors are common.