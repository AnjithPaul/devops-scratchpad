#networking 
## OSI

### Physical Layer - Layer 1
- [ ] basically just sends all data, **no additional logic**. so could have collision between multiple devices sending data at same time.
- [ ] actual physical connection between the devices.
- [ ]  **0s and 1s**
- [ ] Hub (just broadcast to all connected device, no routing to specific device), Repeater, Modem, Cables

### Data Link Layer  - Layer 2
- [ ] wait till layer 1 is not transmitting, then pass data to layer 1 to send. will detect collision and wait for random time before trying again.
- [ ] node-to-node delivery of the message
- [ ]  make sure data transfer is error-free
- [ ] **MAC address**.
- [ ] Address Resolution Protocol
	- [ ] “Who has that IP address?” and the destination host will reply with its MAC address.
- [ ] **frames**
    - [ ] header
        - [ ] preamble
        - [ ] destination mac address
        - [ ] source mac address
        - [ ] layer3 protocol (e.g: ip)
    - [ ] payload
        - [ ] data from layer 3
    - [ ] frame check sequence - check corruption
- [ ] Switch (has MAC Address-port table to send data to right device) & Bridge

### Network Layer - Layer 3
- [ ]  transmission of data from one host to the other located in **different networks**
- [ ] packet routing i.e. selection of the shortest path to transmit the packet
- [ ] **IP address**
- [ ] **Packet**
    - [ ] TTL/Hop Limit - time to live - max no of hops it can do before being discarded
    - [ ] protocol - tcp, udp, ICMP
    - [ ] source ip
    - [ ] destination ip
    - [ ] data from layer 4
    - [ ] some other stuff
- [ ] routers
    - [ ] L3 packets go through multiple networks(routers). each router will encapsulate the packet in a new frame and discard the frame from previous router.
- [ ] 

### Transport Layer - Layer 4
- [ ] End to End Delivery of the complete message.
- [ ] acknowledgement of the successful data transmission and re-transmits the data if an error is found.
- [ ] port number
- [ ] Segments
- [ ] Firewall
- [ ] TCP, UDP

### Session Layer - Layer 5
- [ ] establishment of connection, maintenance of sessions, authentication, and also ensures security.\
- [ ] Message
- [ ] Gateway

### Presentation Layer - Layer 6
- [ ] Translation layer
- [ ] data from the application layer is extracted here and manipulated(translation/encryption/compression) as per the required format to transmit over the network.


### Application Layer - Layer 7
- [ ] produce the data
- [ ] displaying the received information to the user.
- [ ] ftp,https