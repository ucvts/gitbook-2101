# Routing

## Addressing

In order for two machines to communicate, there needs to be a way for them to _find_ each other. Just like we use street addresses and postal codes to locate a person's physical address, there are Internet addresses used to locate machines in a network.

{% embed url="https://www.youtube.com/watch?v=GiYJ\_RB21oo&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Every device connected to the Internet has a unique address. When data is sent, it includes both a _to_ address and a _from_ address. The address format follows a standard, agreed upon format.

### Internet Protocol

This protocol defines the format of an Internet address \(typically called an IP address\).

Historically, IP addresses are broken down into four numbers \(separated by dots\).

```text
93.184.216.34
```

The address itself is hierarchical, meaning each number in the sequence further specifies the device being targeted. The leftmost number in the series is the broadest, whereas the rightmost is the most specific.

| 93 | 184 | 216 | 34 |
| :--- | :--- | :--- | :--- |
| Network | Subnetwork | Sub-subnetwork | Device |

With this in mind, we can use partial IP addresses to identify entire networks.

* 93.x.x.x identifies the entire network.
* 93.184.x.x identifies the entire subnetwork.
* 93.184.216.x identifies the entire sub-subnetwork.

This format is scalable, and makes it easy to add more networks and more devices.

#### IPv4

IP addresses are 32-bit numbers. Each value can be anything from 0 through 255, which can be represented by an 8-bit number. And since we have four of these numbers, that's how we get to 32 bits.

Using 32-bit IP addresses, we can uniquely represent over 4 billion devices. The 32-bit version is called IPv4, and has been around since the 1980s. Although it isn't quite outdated yet, we'll soon have well over 4 billion devices and IPv4 won't cut it anymore.

#### IPv6

This is a new version of the Internet Protocol that uses 128 bits to address each device. This gives us 340,282,366,920,938,463,463,374,607,431,768,211,456 unique address, which should be _plenty_ for the foreseeable future!

IPv6 addresses are represented using eight, four-digit hexadecimal values.

```text
2001:0DB8:AC10:FE01:34F7:6789:9876:DCB1
```

It follows the same hierarchical structure, just with many more possible combinations.

#### IETF

The [International Engineering Task Force \(IETF\)](https://www.ietf.org/) is an open community of engineers, designers, vendors, and researchers whose primary focus is the evolution and functionality of the Internet.

## Viewing a Website

This seems like a pretty menial task, and certainly not something you need to be taught how to do. And, in fact, you're right. It's easy, and that's by design!

{% embed url="https://www.youtube.com/watch?v=jrTS0anDwss&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

URL stands for Uniform Resource Locator, and it's what you type into URL bar to access a website. Something like `www.google.com` or `www.facebook.com` are URLs.

A _resource_ is one of many things we many want to access on the Internet. A website, a picture, a video. When we type the URL into the browser, the browser needs a way of locating it. Suppose we're looking to access `www.example.com/homepage.html`.

`www.example.com` is called the domain, and it's _where_ on the Internet the browser will look for the resource. `homepage.html` is called the path, and it's _what_ resource you're requesting.

When you type this into the browser, you're making a _request_.

> _Hi, example.com! Can you send me the homepage.html file?_

If `www.example.com` is located, and it has a `homepage.html` file, it sends this file back to the browser in the form of a _response_. Once the browser receives the file, it'll render it \(or download it to your computer in some cases\).

This all happened very quickly and at a very high level. In the next couple sections, we'll go into more detail about how exactly this process takes place.

### Domain Name System

The Domain Name System \(DNS\) is responsible for translating between IP addresses and human-readable URLs. Remember, every device on the Internet as an IP address. Even though we type in `www.google.com`, the request-response process that takes place using the underlying IP address.

{% embed url="https://www.youtube.com/watch?v=np-BwM\_c3vk&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

DNS is responsible for mapping URLs to IP addresses.

| URL | IP Address |
| :--- | :--- |
| www.google.com | 172.217.18.174 |
| www.codehs.com | 93.184.216.34 |
| www.wikipedia.org | 91.198.174.192 |

The DNS is a hierarchical set of servers, each responsible for subset of name-address pairs.

* Root server

The root server is at the top of this hierarchy, and its where your request originates.

* Top-level domain server

This is the second stop. Top-level domains include things like `.com`, `.org`, and `.edu`.

* Second-level domain server

This is the website itself: Google, Wikipedia, CodeHS.

* Subdomain server

This is the resource within the website that you wish to access: `homepage.html`, `something.jpg`.

## Determining the Route

When we send data from one computer to another, we know we need to include a to- and from-address. The routers that make up the Internet determine _how_ the data is sent between those addresses.

{% embed url="https://www.youtube.com/watch?v=Sb3F0jNytJs&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

When we send data, our computer will forward the information to the router with the lowest cost. This is a bit of an oversimplification, but cost is generally determined using proximity, trustworthiness, and speed of connection. This process continues, with our data being forwarded from router to router, until it reaches our intended destination.

All of these routers are connected, which builds a degree of redundancy into the network. There always exists more than one path between two points. This is by design. It creates a reliably, fault-tolerant network. If a router or two go offline, we can still be sure our message will be delivered.

This improves the scalability, and thus performance, of the network as a whole.

