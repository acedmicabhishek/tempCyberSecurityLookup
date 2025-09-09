# MODULE 5: Application Layer

The Application Layer is the seventh and topmost layer of the OSI model. It is the layer that is closest to the end user, and it provides the interface between the applications we use and the underlying network. The Application Layer is responsible for providing services that directly support user applications, such as file transfer, email, and web browsing.

## Application Layer Protocols

Application Layer protocols define the rules for communication between application programs.

### DNS (Domain Name System)
The Domain Name System (DNS) is a hierarchical and decentralized naming system that is used to translate human-readable domain names (e.g., www.google.com) into machine-readable IP addresses (e.g., 172.217.168.68). This is a critical service on the Internet, as it allows users to access websites and other resources using easy-to-remember names rather than numerical IP addresses. DNS uses a distributed database system, where the responsibility for resolving domain names is delegated to a hierarchy of DNS servers.

### SMTP (Simple Mail Transfer Protocol)
SMTP is the standard protocol for sending email messages over the Internet. When you send an email, your email client uses SMTP to send the message to your email server. The email server then uses SMTP to send the message to the recipient's email server. SMTP is a "push" protocol, meaning that it is used to send messages from a client to a server.

### POP (Post Office Protocol)
POP is a protocol that is used by email clients to retrieve email messages from a mail server. The current version is POP3. When an email client uses POP3, it typically downloads the messages from the server to the local computer and then deletes them from the server. This can be problematic if you want to access your email from multiple devices.

### IMAP (Internet Message Access Protocol)
IMAP is another protocol for retrieving email messages from a mail server. Unlike POP3, IMAP allows the user to view and manage their email messages directly on the server. This means that any changes you make to your email (e.g., deleting a message, creating a folder) will be reflected on all of your devices.

### FTP (File Transfer Protocol)
FTP is a standard network protocol that is used to transfer files from one host to another over a TCP-based network, such as the Internet. FTP is built on a client-server architecture and uses separate control and data connections between the client and the server. The control connection is used to send commands and receive responses, while the data connection is used to transfer the actual files.

### HTTP (Hypertext Transfer Protocol)
HTTP is the foundation of the World Wide Web. It is an application protocol that is used to request and transmit files, especially web pages and web page components, between a web server and a web browser. HTTP is a stateless protocol, meaning that each request is treated as an independent transaction, and the server does not keep any information about previous requests.

## Basics of Wi-Fi
Wi-Fi is a wireless networking technology that is based on the IEEE 802.11 family of standards. It allows devices to connect to a network without the need for physical cables. Wi-Fi networks operate in the 2.4 GHz and 5 GHz radio bands. A typical Wi-Fi network consists of a wireless access point (AP), which is connected to a wired network, and one or more wireless clients, such as laptops, smartphones, and tablets. Wi-Fi security is a major concern, and several security protocols have been developed to protect Wi-Fi networks, including WEP, WPA, and WPA2.