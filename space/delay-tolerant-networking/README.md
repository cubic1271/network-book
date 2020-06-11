# Delay-Tolerant Networking

The most common definition of DTN is codified in [RFC 4838](https://tools.ietf.org/html/rfc4838), which was originally published in April of 2007.  Quoting the abstract:

> ```text
>    This document describes an architecture for delay-tolerant and
>    disruption-tolerant networks, and is an evolution of the architecture
>    originally designed for the Interplanetary Internet, a communication
>    system envisioned to provide Internet-like services across
>    interplanetary distances in support of deep space exploration.
> ```

This quote suggests that DTN exists to solve two fundamental problems that exist in the area of space networks.  One challenge is associated with delay, and the other challenge is associated with disruption.  Before explaining how DTN addresses each of these challenges, however, it is necessary to begin with an overview of why each challenge exists.

Delay is a challenge in space environments largely due to the huge distances involved.  To understand why, first recall that a signal can only ever travel as quickly as the speed of light \(or 299792 km / sec, which will be rounded up to 300000\).  Now, if we consider distances to various objects in the solar system:

| Target | Distance | Propagation Delay |
| :--- | :--- | :--- |
| [Low Earth Orbit](https://en.wikipedia.org/wiki/Low_Earth_orbit) | &lt;2,000 km | &lt;1 msec |
| [Geostationary Orbit](https://en.wikipedia.org/wiki/Geostationary_orbit) | 35,786 km | 120 msec |
| [Moon](https://www.wolframalpha.com/input/?i=distance+from+earth+to+moon+in+kilometers) | 395,211 km | 1.3 sec |
| [Lagrange Point \(L1\)](https://en.wikipedia.org/wiki/Lagrangian_point) | 1,500,000 km | 5 sec |
| [Venus](https://www.wolframalpha.com/input/?i=distance+to+venus+in+kilometers) | 44,450,000 km | 2.5 min |
| [Mars](https://www.wolframalpha.com/input/?i=distance+to+mars+in+kilometers) | 141,000,000 km | 7.8 min |
| [Jupiter](https://www.wolframalpha.com/input/?i=distance+to+jupiter+in+kilometers) | 644,300,000 km | 36 min |

As delay increases, communications tend to become more complex.  For example, assuming that one wishes to push a file to Venus via TCP, one must wait at least 5 minutes \(2.5 minutes out, and another 2.5 minutes back\) to determine whether each individual segment was successfully received.  Generally, it's wise to avoid using TCP on individual links that exceed around 6,000,000 km \(or a latency of ~30 seconds\) in length.

The other challenge in space networks involves the idea of disruption.  Radio signals cannot propagate through large objects \(e.g. the surface of the Earth, the moon, other planets, other moons, _etc._\).  Also, there are fewer ground stations than there are spacecraft which want to use them.  As such, it is generally not feasible to keep spacecraft connected to one another for extended periods of time.  Instead, spacecraft schedule periods of time \(called _**events**_\) when they can establish and keep a link, and will batch all necessary data and telemetry into transmissions that occur during the event window.

To understand where disconnection becomes a problem from a solar system internet perspective, we need to make some assumptions about the way the internet will develop in space.  The first assumption we make is that our mode of operation will not fundamentally change - instead, we will have assets that can only talk to one another at very limited times.  We also assume that the space internet evolves into an architecture that allows data to make more than one logical hop before reaching its destination.

In the event of a multi-hop network with intermittent disconnection, another issue begins to appear.  Modern networking protocols operate under the assumption that an instantaneous path exists between a specific source and a specific destination.  However, in a space network, this is not necessarily the case: assuming I'm trying to move data from Pluto to Earth, I may want to move data from Pluto to Jupiter today, and then from Jupiter to Earth tomorrow.  Connection-oriented protocols don't offer a terribly effective way to support such a strategy.

Both of these issues are extremely complex, and trying to address them without carefully managing their complexity would be a substantial challenge.  Thus, RFC 4838 summarizes its approach to delay- and disruption- tolerance.  It describes:

> ```text
> a message-oriented overlay that exists above the transport (or other) 
> layers of the networks it interconnects.
> ```

So what is an overlay?  Fundamentally, an overlay is a means to compose a virtual network on top of another.  For example, when one uses a VPN to connect to a corporate network, they essentially establish their system as a logical extension of the corporate network despite being physically separated from the wires and systems that compose said network.  For example, looking at the figure below:

![Defining a network overlay](../../.gitbook/assets/image%20%288%29.png)

We assume that we have a complex network consisting of nodes A through H, and that they are connected to one another as shown.  An overlay would involve taking A, B, and C, and turning them into a separate logical network.

