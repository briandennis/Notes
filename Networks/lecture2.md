# Lecture - 1/19

## Application Requirements

1. Scalable connectivity
2. Cost-effective Sharing
3. Supporting common services

## Switched Networks
Uses switches. Can be used to build internetworks - Internet using routers.

There is a special element called a **switch** that hosts connect to. Hosts have one link going out of them, send and receive messages. Switches can receive messages from multiple links and forward them. Switches don't run applications, they receive messages and send them out.

Switches have a table that maps:

host → Link

h2 → l4

h3 → l5

The action of getting a message, looking up in the table, and sending out to the link is called **switching** or **forwarding**.

### Kinds of Switches

Circuit switches - pre established route, labels the exact path a message will go.

Packet Switches - Take a message, break it into packets. Each packet is individually switched in the network.


## Routers

>Switched networks do not scale because tables can only be of a limited size.

Build up multiple switched networks connected by router.

SN1 ↔ R1 ↔ SN2 ↔ R2 ↔SN3 ↔ R3


Routers are similar to switches. In switch tables what you hold is host/hardware addresses and L2/Mac addresses. Router tables are based on network addresses. IP addresses tell you something about where you're located in the network. Every host has not only a MAC address, but also an IP address.

128.105 - UW

## Internetwork

The entity that is composed of multiple switched networks connected with routers. Single admin entity. Recursively do this to build the internet.

## Cost Effective Resource Sharing

- Packet switching
- Statistical mux (multiplexing)

### Packet Switching

 Two main problems with circuit switching:

1. Circuit establishment overhead - Switch maintain a lot of dynamic information about each active circuit. Also must tear down circuit.

2. Wasted resources - bandwidth reservations.

Packet switching to the rescue!

Message is split into multiple packets, individually addressed to destination. Switches, routers deal with each packet individually.

Track static table of entries so not as much overhead. No bandwidth or performance guarantee.

### Statistical Mux

How do packets from different apps, share the network? Multiplexing!

Time division mux (TDM) - Problems include how do you slice up time without knowing how many apps? App may not have anything to say during its time slot.

Frequency division mux (FDM) - Link of capacity C. N apps, each of which gets C/N bandwidth. Problems are similar: may waste bandwidth and don't know how many apps.

Statistical mux - Apps take turns, but apps can send data on demand.

How?

1. Buffering
2. Maximum transmission unit (MTU)

#### Buffering

Messages are sent as a sequence of packets. When into the switch, buffered into a queue with a corresponding policy (FIFO). Packet is the atomic unit. Big packets can drown out small packets.

If drain rate < load, buffers fill up and packets will be dropped. Called **congestion**.

> Internet will make its "Best Effort"

#### MTU

Maximum packet size on link. ~ 1500B

## Supporting Common Services

- Identify common requirements. Use software to encode these and allow apps to leverage them. This is done through layering and protocols. Logical channels of communication.

App 1 ↔ App 2

Some want reliability, some don't care and want it fast.

### Transport Layer

two main protocols:

1. Transmission Control Protocol (TCP) - reliable.
2. User Datagram Protocol (UDP) - unreliable.
