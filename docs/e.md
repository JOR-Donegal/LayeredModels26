# Layer 5, 6, 7

!!! abstract "Session, Presentation and Application Layers"

The top layers of the model are less easy for us to map to real purposes in data communication and tend to get aggregated together by us networking people. 

In theory layer 5 maintains session information between two hosts (but didn’t we do that with TCP at layer 4?). 

Layer 6 is about presenting data to the final application, which lives at layer 7. 

The reality, some of our protocols bridge layers, break layers, etc. It is after all, only a model.

<figure>
<img src = "https://jor-donegal.github.io/LayeredModels26/images/fig5.png">
<figcaption>Fig 5. Layer summary.</figcaption>
</figure>

The ultimate way to secure hosts is to have a firewall which is _application aware_. We call these layer 7 firewalls or proxies and we can use them to monitor and control traffic even where it uses anomalous ports. 

We can take a similar approach to securing services; we can use a _Web Application Firewall_ (WAF), where the traffic to and from a server is understood at the application level.