# Layer 1

!!! abstract "The Physical Layer"

The first layer in any data communications system will be the physical layer. This is where we describe the wires or cables of radio waves, the electrical or optical properties, signal levels and encoding. 

For example, the ubiquitous structured cabling which we use for computing is called CAT5e or CAT6 and the most common protocol is Ethernet. Signals on this cable have; 

- An electrical level for symbols; Ethernet has five levels, rather than just ones and zeros.
- A bit rate of 250Mbps per pair over four pairs
- An encoding scheme to increase the amount of information per symbol
- An error correction scheme 

We could also look at the standards for transmitting Ethernet over 

- Fibre optics; the physical parameters would be different (light frequency, encoding etc.), but we would still be transmitting Ethernet. 
- Radio; the physical parameters would be wavelength, channel width, signalling, but we would still be transmitting Ethernet. 

At layer 1 we find the physical connections and properties to allow for data communications. 

When someone talks about a layer 1 problem, they mean a wire is broken, there is radio noise, or fibre optic cables need cleaning. The devices at layer 1 are cables, transceivers, signal repeaters. We can connect computers together at layer 1 by running a cable between them of using a multi-port repeater called a hub. 

In your own time, read about ISO11801, it’s the standard that defines hierarchical wiring of networks for the Enterprise. It might also be worthwhile checking TIA-942 which describes data centre wiring (amongst other things) in the US. Or perhaps the newer European EN50600 series of standards for data centres.
