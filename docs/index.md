# Introduction

!!! abstract "Layered Models"

Once systems become very complex, they can become unmanageable. I don’t know if anyone has a rule of thumb, but if not, I’ll claim this one (JOR’s first law of complexity!). 

__When you double the number of components in a system, you square its complexity.__

So, there we have it, a completely new hypothesis (arbitrary and unproven) in the lexicon of Science! 

Is it true…… I have no idea! 

Does it roughly describe what we experience…yes! 

For much of the past 60 years we have struggled with the notion of complexity. We really started understanding the magnitude of the problem as very complex projects occurred; the space race in the 1960s resulted in the development of many new forms of logistical planning and tracking. 

For a while, we found ways of mitigating the problems of complexity. We had seen spaghetti code; programs which were so complex and unwieldy as to be unmaintainable. We addressed those problems with structure, functions and later object orientation and code reuse. In early UNIX development, the folks had a great ideology; each tool does one and one job only. Make each tool as simple as possible. This was a great way of mitigating some of the early issues. 

In telecommunications, we often take the same approach. Suppose we look at the physical way of connecting things. We could use wires of many different types, fiber optics, radio, smoke signals, [carrier pigeons](https://www.rfc-editor.org/rfc/rfc1149) etc. Does an application like a web browser need to know how data packets are being carried? 

Probably not.

The easy way to approach these things is to compartmentalize all the things we want to be able to do into layers and let each layer be independent of the others. If we need to change a layer, we just need to worry about its inter-connectedness to other layers, not what is in the layer itself. So an application which can work on a modem, can work on Ethernet or on a radio network.

In the early days of development of this layered approach to communications there were many contributors, none of whom agreed. The result was a compromise which didn’t really suit anybody, but that we still use to this day to describe the layers and inter-relations in a communications model. 

In the next few pages, we will look at how layered models allow us to describe how nodes (computer, printers, etc.) connected to networks and interconnect with each other. In each case we will look at the most typical protocols you are likely to be exposed to. Keep in mind that there are many other alternatives out there! I will examine the _ISO/OSI model_ (they  really called it that!). 

In the ISO/OS model, if you concatenate the first two, and the top three layers of this model, you have the _TCP/IP Model_. Do a little background reading on this. 