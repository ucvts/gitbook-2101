# Protocols

## Packets

When we send information from one machine to another, that information is broken up into small chunks called packets. These packets are sent individually, where they are reassembled upon delivery. Every packet contains metadata \(i.e., data about the data\), which includes a from-address, to-address, as well as the size of the data.

{% embed url="https://www.youtube.com/watch?v=F0dY05FHS50&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

### Internet Protocol

The layout of a packet is governed by the Internet Protocol \(IP\). All packets must contain the following.

* A destination IP address
* An origin IP address
* The actual data being sent

Using only the Internet Protocol, two computers on a network can send single packets to each other.

### Transmission Control Protocol

If you want to send more than one packet, you need the Transmission Control Protocol \(TCP\). This enables multiple packets to be sent, verifies that all packets have arrived, and handles reassembling these packets in the correct order.

IP puts the destination and origin address, as well as the data itself, into the packet. TCP adds a packet number, allowing it to track each packed and reassemble them upon receipt. This is important; packets rarely arrive in the same order they were sent. Additionally, TCP can request packets that didn't arrive to be resent.

Together, TCP/IP define the _metadata_ of a packet, and handle the process of breaking down, sending, receiving, and reassembling information.

* Destination address
* Origin address
* Message size
* Order number

## Requests and Responses

In order for devices to effectively communicate, we need to standardize the process of talking to a web server. This standardization is done through the HyperText Transfer Protocol \(HTTP\).

A typical HTTP request contains the following.

* Request type
* Host
* Content type
* Content language

It looks something like this.

```text
GET /index.html HTTP/1.1
Host: www.example.com
Content-Type: text/html
Content-Language: en
```

When a web server responds to such a request, it generates a similar message.

* Response code
* Server
* Content type
* Content language

It looks more or less the same.

```text
HTTP/1.1 200 OK
Server: MyServer
Content-Type: text/html
Content-Language: en
```

TCP/IP, DNS, and routers work together to send packets over the Internet. HTTP ensures that the information contained within these packets can be properly understood and interpreted.

