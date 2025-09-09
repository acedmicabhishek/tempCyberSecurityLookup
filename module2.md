# MODULE 2: Data Link Layer

## Flow Control and Error Control Protocols
The Data Link Layer provides reliable data transfer through flow and error control mechanisms.

### Stop and Wait
In this protocol, the sender sends one frame and waits for an acknowledgment (ACK) from the receiver before sending the next frame. This ensures that the receiver has enough time to process the frame.

### Go-Back-N ARQ
Go-Back-N ARQ improves upon the Stop and Wait protocol by allowing the sender to transmit multiple frames (a "window") before waiting for an ACK. If a frame is lost or damaged, the receiver sends a negative acknowledgment (NACK), and the sender retransmits that frame and all subsequent frames in the window.

### Selective Repeat ARQ
Selective Repeat ARQ is a more efficient version of Go-Back-N. The sender can still transmit multiple frames, but if a frame is lost or damaged, the receiver sends a NACK for only that specific frame. The sender then retransmits only the lost or damaged frame, not the entire window.

### Sliding Window
The sliding window is a theoretical concept that forms the basis for Go-Back-N and Selective Repeat ARQ. It allows for a continuous flow of data by enabling the sender to transmit a certain number of frames before receiving an ACK. The "window" slides as frames are acknowledged.

## Multiple Access Protocols
These protocols are used to coordinate access to a shared communication medium.

### Pure ALOHA
In Pure ALOHA, a station can transmit a frame at any time. If a collision occurs (i.e., two or more stations transmit at the same time), the frames are destroyed, and the stations wait a random amount of time before retransmitting.

### Slotted ALOHA
Slotted ALOHA divides time into discrete intervals called slots. A station can only transmit at the beginning of a slot. This reduces the probability of collisions compared to Pure ALOHA.

### CSMA/CD (Carrier Sense Multiple Access with Collision Detection)
With CSMA/CD, a station listens to the channel before transmitting. If the channel is idle, it transmits. If the channel is busy, it waits. If a collision is detected during transmission, the station stops transmitting and sends a jam signal to inform other stations of the collision.

### CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)
CSMA/CA is used in wireless networks. Before transmitting, a station sends a "request to send" (RTS) signal. If it receives a "clear to send" (CTS) signal from the receiver, it transmits the data. This helps to avoid collisions, which are more difficult to detect in wireless environments.

## Error Detection and Error Correction
These techniques are used to ensure the integrity of data during transmission.

### Fundamentals
-   **Error Detection:** The ability to detect errors that have occurred in a transmitted frame.
-   **Error Correction:** The ability to correct errors that have occurred in a transmitted frame.

### Block Coding
In block coding, the message is divided into blocks of k bits, and r redundant bits are added to each block to make a codeword of n = k + r bits.

### CRC (Cyclic Redundancy Check)
CRC is an error-detecting code commonly used in digital networks and storage devices to detect accidental changes to raw data. A short check value, based on the remainder of a polynomial division of their contents, is appended to the data.

### Hamming Code
Hamming code is a set of error-correction codes that can detect up to two-bit errors or correct one-bit errors without detection of uncorrected errors.