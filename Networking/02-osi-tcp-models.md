# 02 Reference Models

- OSI and TCP-IP models are frameworks to showcase how the information travel accross networks. They are a way to understand how networks talk to each other.

- These models are divided into layers. Each layer has its own responsability and only talk with the layers directly below and above it.

- How do we use these two models? OSI it primarily used to help troubleshoot networks. If something is not working we can start at the first layer in the OSI model and if everything is okay at this level we can move up to the next layer until we find where the problem is. While the TCP-IP model is actually used to implement the communication in modern networks. It can consist of 4 layers or 5 layers depending on the variation.

- The communication in the same layer level happens through protocols. When you send information, it travels from layer 7 to layer 1 on sender's device (encapsulation), and from layer 1 up to layer 7 on the receiver's device (decapsulation).

## OSI

- Layer 7 Application Layer: Eesponsible for providing network services directly to the user's applications.
- Layer 6 Presentation Layer: Responsible for formatting, encoding, and encrypting data.
- Layer 5 Session Layer: It is in charged in of which conversation belongs to which connection.
- Layer 4 Transport Layer: Responsible for the end-to-end delivery of data between services using ports. This is where TCP and UDP operate. TCP guarantees delivery, UDP prioritizes speed.
- Layer 3 Network Layer: It is in charged of the transmition between nodes in different networks.
- Layer 2 Data Link Layer: It is in charged of transmition between nodes in the same network
- Layer 1 Physical Layer: It is in charged of the physical transmision, electrical signals, laser signals and cables

## TCP-IP

- Layer 4 Application -> OSI 5, 6, 7
- Layer 3 Transport -> OSI 4
- Layer 2 Internet -> OSI 2, 3
- Layer 1 Network Access -> OSI 1
