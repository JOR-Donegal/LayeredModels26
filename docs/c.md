# Layer 3

!!! abstract "The Inter-Network Layer"

Layer 2 allows two devices on the same network to talk to each other using addresses which are unique to every network card. This works because it’s easy to keep track of the few dozen (or few hundred) devices that are on the same network. 

That makes layer three easy to explain. Layer 3 allows devices on different networks to talk to each other and the most common protocol we use for this is Internet Protocol (IP). We can’t locate all these devices based on their unique addresses, or we would have to know the network path to every individual device in the world AND track then as they move around. Layer 3 works by assigning a block of addresses to a network and then telling the whole world where to find that block of addresses. These blocks can be big enough to accommodate millions of nodes, or as small as 256 nodes.

When a node joins a network, it keeps its layer 2 (Ethernet) address, but it is also given a layer 3 (IP) _logical_ address. We now construct a layer 3 _packet_ for sending to another network. It has IP addresses which are globally significant and unique. Every network in the world knows how to find every other network, so once we know what network a node is part of, we can route packets to that network and hence to that node. 

We _encapsulate_ the IP packet as the data field in the Ethernet frame and we use the Ethernet frame to transport the packet around the local network. To get to another network, the Ethernet frame has to terminate in a _router_, a device which routes packets at layer 3. The router strips the Ethernet frame off and forwards the IP packet to the next nearest router to its destination. The links between routers may be Ethernet or some other layer 2 protocol. We don’t care; layer 2 is how the devices communicate with each other locally only. The layer 3 packet is passed from router to router until it gets to its destination network.

<figure>
<img src = "https://jor-donegal.github.io/LayeredModels26/images/fig2.png">
<figcaption>Fig 2. An IPv4 packet encapsulated.</figcaption>
</figure>

To secure a network subnet at layer 3, we use a router with _Access Control Lists_ (ACLs) or we can use a firewall.