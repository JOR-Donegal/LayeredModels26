# Layer 4

!!! abstract "The Transport Layer"

So now we have Layer 3, a way of communicating from a node on one network to any other node on any other network. The next thing we must worry about is the quality of that communication. 
- How do I know if a packet of data I send is received? 
- How do I tune my communications to the vagaries of the many links from end-to-end? 

These things we do at layer 4.

## Transmission Control Protocol (TCP)
The first trick we have is to ensure that if a packet is lost, we can identify it and ask for a resend of exactly that packet. Or if packets arrive out of sequence that we can rearrange the data into the correct order. We do this by numbering each packet we send with a unique 32-bit _sequence number_. Each packet sent is acknowledged by a return packet which also has a unique 32-bit number. Rather than sending packets into a black hole, the effect of this is to establish host to host communications. 

TCP also includes a _flow control_ mechanism. We could send just one packet and wait for an acknowledgement, but this would be very slow. A better way to send packets is to use a sliding window. The sender will send a fixed number of packets before getting an acknowledgement. If everything works, the sender will now increase the number of packets it will send without waiting for an acknowledgement. Eventually, packets will be lost and the sender will reduce the number of packets in transit again, a sliding window. There are many other features in the TCP stack, some of the features are arguably layer 5. Do some background reading on it.

TCP is encapsulated in the IP packet.

<figure>
<img src = "https://jor-donegal.github.io/LayeredModels26/images/fig3.png">
<figcaption>Fig 3. TCP Encapsulation.</figcaption>
</figure>

## User Datagram Protocol (UDP)
Many network applications do not require reliable host to host communications. For example, if we are streaming audio or video, there is no point adding back a missing frame two seconds after it should have been in the audio stream. We also have multi-cast traffic; traffic which egresses from one node but is received by many. UDP provides an unreliable service and datagrams may arrive out of order, appear duplicated, or go missing without notice.

UDP is encapsulated in the IP packet.

<figure>
<img src = "https://jor-donegal.github.io/LayeredModels26/images/fig4.png">
<figcaption>Fig 4. UDP Encapsulation.</figcaption>
</figure>

## Ports
We may establish communications between two hosts for a purpose; for example, a web server and client. 

But how would we allow another application to run between the two hosts at the same time?

How we would distinguish between packets for each application? 

We do this by using _port numbers_. There is a 16-bit field in the headers of the UDP and TCP protocol which allow us to distinguish one application from another and multiplex multiple protocols to the same IP address. For example, 

- All unencrypted web traffic will arrive with a destination port of 80
- All encrypted web traffic will arrive with a destination port of 443
- All Telnet traffic will arrive with a port number of 23, etc.

## Security
We can keep a track of the applications which run across our networks based on port numbers, but this is very over simplistic, as malware can use a well-known port and be mistaken for a genuine application. Standard firewalls do this.

On a LAN, we can use protocols like IPSEC to secure file sharing, in my experience, this is rarely done. 

In the wide are, we use VPNs to secure sessions, based on IPSEC or Secure Sockets Layer (SSL), which these days is Transport Layer Security (TLS).