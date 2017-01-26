# Sockets

Network Application

Layer 2 - Ethernet/MAC
Layer 3 - IP
Layer 4 - TCP/UDP

* abstraction is in terms of messages not packets
* most OS provide these basic methods to interact
  * create
  * bind
  * listen
  * accept
  * connect
  * send

## Process

### Server
* create a socket
  * S = Socket(NETWORK, SOCK-STREAM, TCP)
* bind(S, address( IP + portNum))
* listen(S, numConnections)
* Accept(S, ...)
* recv(client1, buffer, len)

### Client
* create a socket
* connect(cs, destination address)
* send()
