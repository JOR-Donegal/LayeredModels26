# Layer 2

!!! abstract "The Data Link Layer"

Layer 2 provides for the standards that let us communicate between two devices which are directly connected to each other or are on the same network as each other. There have been many standards at layer 2, such as token bus and token ring, ATM, FDDI (feel free to look these up). However, Ethernet is the most common modern standard for communications between two nodes on the same network.

<figure>
<img src = "https://jor-donegal.github.io/LayeredModels26/images/fig1.png">
<figcaption>Fig 1. An Ethernet Frame.</figcaption>
</figure>

We will look in more detail at the Ethernet frame in later exercises. However, every network card has a unique 48-bit _Media Access Control_ (MAC) address, unique in the whole world and standardized. 

The sending node sends out a frame with a destination address (so the computer the frame is intended for knows that the frame is for it) and its own address, a data payload. The standard includes for things like knowing when the network is busy or free, identifying when frames of data have got mangled or when two devices try to communicate at the same time and talk over each other (called a _collision_).

To connect computers at layer 2, we need active devices which understand MAC addresses and can keep a track of them. A device like this is called a bridge. The most common device in a modern enterprise or data centre is the multi-port bridge, known as a switch. 
Where we need to secure a network segment at layer 2, we can use a transparent or layer 2 firewall.
