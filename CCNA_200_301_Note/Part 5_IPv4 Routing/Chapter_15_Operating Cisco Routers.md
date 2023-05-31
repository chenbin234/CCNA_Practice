# Operating Cisco Routers

### 1. **Installing Cisco Routers**

<img src="images/image-20230531105609302.png" alt="image-20230531105609302" style="zoom:50%;" />

<img src="images/image-20230531110347468.png" alt="image-20230531110347468" style="zoom:50%;" />

**Network Interface Modules (NIMs)**

Gi0/1 refers to interface GigabitEthernet0/1 and is an RJ-45 port that supports UTP cabling only. However, interface Gi0/0 (short for GigabitEthernet0/0) has some interesting features:

- The router has two ports for one interface (Gi0/0).
- You can use one or the other at any point in time, but not both.
- One physical port is an RJ-45 port that supports copper cabling (implying that it is used to connect to a LAN).
- The other Gi0/0 physical port is a Small Form Pluggable (SFP) port that would support vari- ous fiber Ethernet standards, allowing the port to be used for Ethernet WAN purposes.

<img src="images/image-20230531110643485.png" alt="image-20230531110643485" style="zoom:50%;" />

**Note that Cisco enterprise routers typically have an on/off switch, while switches do not.**

The terms **enterprise router** and **small office/home office (SOHO)** router act as a pair of contrasting categories for routers,

### 2. **Enabling IPv4 Support on Cisco Router Interfaces**

A couple of topics do work differently with the router CLI as compared to the switch CLI, as follows:

<img src="images/image-20230531112039022.png" alt="image-20230531112039022" style="zoom:50%;" />

#### 2.1 **Router Interfaces**

Routers support a variety of other types of interfaces, including serial interfaces, cable TV, DSL, 3G/4G wireless, and others not mentioned in this book.

Two of the most common commands to display the interfaces, and their status, are the
 **show ip interface brief** and **show interfaces** commands. 

<img src="images/image-20230531112651351.png" alt="image-20230531112651351" style="zoom:50%;" />

<img src="images/image-20230531112707367.png" alt="image-20230531112707367" style="zoom:50%;" />

**Interface Status Codes**

<img src="images/image-20230531125142614.png" alt="image-20230531125142614" style="zoom:50%;" />

<img src="images/image-20230531125208923.png" alt="image-20230531125208923" style="zoom:50%;" />

**Router Interface IP Addresses**

- Most Cisco router interfaces default to a disabled (**shutdown**) state and should be enabled with the **no shutdown** interface subcommand.
- Cisco routers do not route IP packets in or out an interface until an IP address and mask have been configured; by default, no interfaces have an IP address and mask.
- Cisco routers attempt to route IP packets for any interfaces that are in an up/up state and that have an IP address/mask assigned.

<img src="images/image-20230531125651845.png" alt="image-20230531125651845" style="zoom:50%;" />

<img src="images/image-20230531125732206.png" alt="image-20230531125732206" style="zoom:50%;" />

<img src="images/image-20230531125834022.png" alt="image-20230531125834022" style="zoom:50%;" />

## **Command References**

<img src="images/image-20230531130106158.png" alt="image-20230531130106158" style="zoom:50%;" />

<img src="images/image-20230531130122996.png" alt="image-20230531130122996" style="zoom:50%;" />
