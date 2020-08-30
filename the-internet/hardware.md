# Hardware

## What is the Internet?

If you can imagine, there was a time before the Internet existed. For many of you, you were born into a high-speed, connected society. This wasn't always the case.

{% embed url="https://www.youtube.com/watch?v=GIWQF9lF8nw&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

As recently as 2005, only 16% of the world was online \(about half of the developed world, but less than 1 in 10 people in the developing world\). By 2014, this percentage jumped to 40%. That's quite a bit of progress, to be sure. However, we're still talking about a world where more than half of the population is offline.

In the modern era, the Internet is ubiquitous. People send 7,136 Tweets and make 2,053 Skype calls every single of every day. Not to mention the 53,242 Google searches and 2.5 million emails \(the majority of which are spam\) sent per second. All of this adds up to over 33 GB of Internet traffic every second.

The Internet is a network of networks, which gives us access to a wealth of information at our fingertips. It's built on open, agreed upon protocols. We're going to learn all about what those protocols are, and how they form the backbone of the Internet in this section.

## Networking Devices

A network is two or more connected machines that can communicate and share information. A simple network might have just two or four interconnected devices, where each device has a direct connection to every other device. While this works in small numbers, it's not scalable for large networks.

{% embed url="https://www.youtube.com/watch?v=KiyCt\_gIbwM&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

A better solution is to introduce a device called a router. A router serves an intermediary device capable of receiving information from one machine, and routing it to another. In more complex networks, these routers often talk to each other to aid in directing traffic to its intended recipient.

The Internet is effectively a macro version of this scenario. It's a network of routers that work together to connect smaller networks of machines.

### Connectivity

Networks use three primary means of sending data.

* Electricity
* Light
* Radio

The primary means by which machines transmit data using electricity is via Ethernet cables. They're cheap to produce and install, but only cover a limited range in terms of connectivity distance. Sending 1s and 0s is pretty simple using an Ethernet cable. A high-voltage transmission is interpreted as a 1, while a low-voltage transmission is interpreted as a 0.

Fiber optic cables use light to transmit data. They can cover a much larger distance compared to Ethernet cables, but they're also much more expensive. Bright and dim lighting are used in the representation of binary 1s and 0s.

WiFi routers and cell towers use radio waves to transmit signals \(and data\). These are ideal for shorter distances, but have the added advantage of being wireless. The frequency of the waves distinguishes between 1s and 0s. High-frequency waves are 1st, while low-frequency waves are 0s.

### Transmission

When we talk about the transmission of data, there are a few important terms that come into play: bandwidth, bitrate, and latency.

Bandwidth is the capacity of data transmission in a given system, and bitrate is how we measure that bandwidth. This translates to the number of bits a system can send per second. Latency is how long it takes a bit to travel from sender to receiver.

Fiber optic connections have the lowest latency \(and therefore fastest connection\). Since we're talking about the speed of light, this comes out to roughly 5 microseconds/kilometer. And although Ethernet connections are typically much shorter than a kilometer, they clock in at roughly 300 microseconds/kilometer.

