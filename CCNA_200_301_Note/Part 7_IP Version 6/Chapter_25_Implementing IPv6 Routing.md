# **Implementing IPv6 Routing**

## 1. **Connected and Local IPv6 Routes**

Specifically, a router adds IPv6 routes based on the following:

![image-20230601220119497](images/image-20230601220119497.png)

### 1.1 **Rules for Connected and Local Routes**

<img src="images/image-20230601220453720.png" alt="image-20230601220453720" style="zoom: 67%;" />

### 1.2 **Example of Connected IPv6 Routes**

Figure 25-1 gives the details of one sample internetwork used in this chapter. The figure shows the IPv6 subnet IDs. The upcoming examples focus on the connected and local routes on Router R1.

<img src="images/image-20230601220757773.png" alt="image-20230601220757773" style="zoom:67%;" />

<img src="images/image-20230601221128564.png" alt="image-20230601221128564" style="zoom:67%;" />

Based on Figure 25-1 and Example 25-1, R1 should have three connected IPv6 routes, as highlighted in Example 25-2.

<img src="images/image-20230601221211274.png" alt="image-20230601221211274" style="zoom:67%;" />

### 1.3 **Examples of Local IPv6 Routes**

<img src="images/image-20230601221339110.png" alt="image-20230601221339110" style="zoom:67%;" />

### 1.4 **Static IPv6 Routes**

<img src="images/image-20230601222055410.png" alt="image-20230601222055410" style="zoom:67%;" />

#### 1.4.1 **Static Routes Using the Outgoing Interface**

<img src="images/image-20230601222125742.png" alt="image-20230601222125742" style="zoom:67%;" />

<img src="images/image-20230601222218116.png" alt="image-20230601222218116" style="zoom:67%;" />

<img src="images/image-20230601222309242.png" alt="image-20230601222309242" style="zoom:67%;" />

#### 1.4.2 **Static Routes Using Next-Hop IPv6 Address**

<img src="images/image-20230601222349726.png" alt="image-20230601222349726" style="zoom:67%;" />

The next few pages walk you through examples, first with a global unicast as a next-hop and then with a link-local as a next-hop.

**Example Static Route with a Global Unicast Next-Hop Address**

<img src="images/image-20230601222733204.png" alt="image-20230601222733204" style="zoom:67%;" />

<img src="images/image-20230601222803047.png" alt="image-20230601222803047" style="zoom:67%;" />

**Example Static Route with a Link-Local Next-Hop Address**

Static routes that refer to a neighbor’s link-local address work a little like both of the preceding two styles of static routes. 

- First, the **ipv6 route** command refers to a next-hop address, namely a link-local address. 
- However, the command must also refer to the router’s local outgoing interface. 
- Why both? The **ipv6 route** command cannot simply refer to a link-local next-hop address by itself because the link-local address does not, by itself, tell the local router which outgoing interface to use.

<img src="images/image-20230601223047920.png" alt="image-20230601223047920" style="zoom:67%;" />

<img src="images/image-20230601223122304.png" alt="image-20230601223122304" style="zoom:67%;" />

**Static Routes over Ethernet Links**

You might have wondered **why the chapter shows examples with a serial link**, knowing that most networks use fewer and fewer serial links today. **Using serial links in the examples avoids one complication when defining static routes that use Ethernet interfaces (LAN or WAN).** 

To configure a static route that uses an Ethernet interface, the **ipv6 route** command’s forwarding parameters should always include a next-hop IPv6 address.

<img src="images/image-20230601223344503.png" alt="image-20230601223344503" style="zoom:67%;" />

<img src="images/image-20230601223417528.png" alt="image-20230601223417528" style="zoom:67%;" />

<img src="images/image-20230601223450780.png" alt="image-20230601223450780" style="zoom:67%;" />

#### 1.4.3 **Static Default Routes**

<img src="images/image-20230601223527215.png" alt="image-20230601223527215" style="zoom:67%;" />

<img src="images/image-20230601223541765.png" alt="image-20230601223541765" style="zoom:67%;" />

<img src="images/image-20230601223602988.png" alt="image-20230601223602988" style="zoom:67%;" />

#### 1.4.4 **Static IPv6 Host Routes**

Both IPv4 and IPv6 allow the definition of static host routes—that is, a route to a single host IP address. With IPv4, those routes use a /32 mask, which identifies a single IPv4 address in the **ip route** command; with IPv6, a /128 mask identifies that single host in the **ipv6 route** command.

<img src="images/image-20230601223745040.png" alt="image-20230601223745040" style="zoom:67%;" />

#### 1.4.5 **Floating Static IPv6 Routes**

<img src="images/image-20230601224119865.png" alt="image-20230601224119865" style="zoom:67%;" />

<img src="images/image-20230601224135840.png" alt="image-20230601224135840" style="zoom:67%;" />

#### 1.4.6 **Troubleshooting Static IPv6 Routes**

<img src="images/image-20230601224237965.png" alt="image-20230601224237965" style="zoom:67%;" />

**The Static Route Does Not Appear in the IPv6 Routing Table**

<img src="images/image-20230601224354444.png" alt="image-20230601224354444" style="zoom:67%;" />

## 2. **The Neighbor Discovery Protocol**

![image-20230601230541532](images/image-20230601230541532.png)

### 2.1 **Discovering Neighbor Link Addresses with NDP NS and NA**

NDP replaces IPv4 ARP using a pair of matched solicitation and advertisement messages: the **Neighbor Solicitation (NS) and Neighbor Advertisement (NA) messages.**

1. Basically, the NS acts like an IPv4 ARP request
2. The NA message acts like an IPv4 ARP Reply, listing that host’s MAC address.

![image-20230601231110229](images/image-20230601231110229.png)

![image-20230601231207358](images/image-20230601231207358.png)

![image-20230601231254853](images/image-20230601231254853.png)

### 2.2 **Discovering Routers with NDP RS and RA**

IPv6 uses the same concept of a default gateway, **but it improves the method for hosts to learn the identity of possible default gateways using NDP.** NDP defines two messages that allow any host to discover all routers in the subnet:

![image-20230601231427681](images/image-20230601231427681.png)

<img src="images/image-20230601231555307.png" alt="image-20230601231555307" style="zoom: 67%;" />

**IPv6 does not use broadcasts, but it does use multicasts.** In this case, the RS message flows to the all-routers multicast address (FF02::2) so that all routers will receive the message. It has the same good effect as a broadcast with IPv4, without the negatives of a broadcast.

### 2.3 **Using SLAAC with NDP RS and RA**

IPv6 supports an alternative method for IPv6 hosts to dynamically choose an unused IPv6 address to use—a process that does not require a server like a DHCP server. The process goes by the name **Stateless Address Autoconfiguration (SLAAC)**

![image-20230601231820831](images/image-20230601231820831.png)

### 2.4 **Discovering Duplicate Addresses Using NDP NS and NA**

IPv6 uses the Duplicate Address Detection (DAD) process before using a unicast address
 to make sure that no other node on that link is already using the address. 

![image-20230601231943746](images/image-20230601231943746.png)



### 2.5 **NDP Summary**

![image-20230601231958111](images/image-20230601231958111.png)

## **Command References**

![image-20230601230837781](images/image-20230601230837781.png)

![image-20230601230852351](images/image-20230601230852351.png)