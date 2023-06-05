# Implementing DHCP

## 1. **Dynamic Host Configuration Protocol**

DHCP uses the following four messages between the client and server. (Also, as a way to help remember the messages, note that the first letters spell DORA):

<img src="images/image-20230604213239071.png" alt="image-20230604213239071" style="zoom:50%;" />

 <img src="images/image-20230604213353868.png" alt="image-20230604213353868" style="zoom:67%;" />

#### 1.1 **Supporting DHCP for Remote Subnets with DHCP Relay**

- Cisco routers can act as the DHCP server, so a distributed design could use the router at each site as the DHCP server.

- However, a centralized DHCP server approach has advantages as well. 

With a centralized DHCP server, those DHCP messages that flowed only on the local subnet in Figure 7-1 somehow need to flow over the IP network to the centralized DHCP server and back. To make that work, the routers connected to the remote LAN subnets need an interface subcommand: the **ip helper-address** server-ip command.

The **ip helper-address** server-ip subcommand tells the router to do the following for the messages coming in an interface, from a DHCP client:

![image-20230604225343926](images/image-20230604225343926.png)

![image-20230604225454386](images/image-20230604225454386.png)



![image-20230604225626875](images/image-20230604225626875.png)

#### 1.2 **Information Stored at the DHCP Server**

![image-20230604225807966](images/image-20230604225807966.png)

Once such interfaces have been identified, the configuration requires the **ip helper-address** interface subcommand on each of those interfaces. For instance, with earlier Figure 7-3, R1’s G0/0 interface needs to be configured with the **ip helper-address 172.16.2.11** inter- face subcommand. 

<img src="images/image-20230604225954354.png" alt="image-20230604225954354" style="zoom: 50%;" />

#### 1.3 **Configuring a Switch as DHCP Client**

<img src="images/image-20230604230036851.png" alt="image-20230604230036851" style="zoom:50%;" />



<img src="images/image-20230604230100309.png" alt="image-20230604230100309" style="zoom:50%;" />

![image-20230604230134884](images/image-20230604230134884.png)

![image-20230604230158555](images/image-20230604230158555.png)

#### 1.4 Configuring a Router as DHCP Client

Just as with switches, you can configure router interfaces to lease an IP address using DHCP rather than using a static IP address, although those cases will be rare.

<img src="images/image-20230604230440895.png" alt="image-20230604230440895" style="zoom:50%;" />



## 2. **Identifying Host IPv4 Settings**

To work correctly, an IPv4 host needs to know these values:

<img src="images/image-20230604230536615.png" alt="image-20230604230536615" style="zoom:50%;" />

#### 2.1 **Host IP Settings on Windows**

<img src="images/image-20230604230851150.png" alt="image-20230604230851150" style="zoom:50%;" />

<img src="images/image-20230604230908098.png" alt="image-20230604230908098" style="zoom:50%;" />

<img src="images/image-20230604230935442.png" alt="image-20230604230935442" style="zoom:50%;" />



#### 2.2 **Host IP Settings on macOS**

<img src="images/image-20230604231026236.png" alt="image-20230604231026236" style="zoom:50%;" />

<img src="images/image-20230604231103719.png" alt="image-20230604231103719" style="zoom:50%;" />

<img src="images/image-20230604231256612.png" alt="image-20230604231256612" style="zoom:50%;" />

#### 2.3 **Host IP Settings on Linux**

<img src="images/image-20230604231403648.png" alt="image-20230604231403648" style="zoom:50%;" />

<img src="images/image-20230604231413533.png" alt="image-20230604231413533" style="zoom:50%;" />

<img src="images/image-20230604231433255.png" alt="image-20230604231433255" style="zoom:50%;" />



## **Command References**

![image-20230604231503362](images/image-20230604231503362.png)

![image-20230604231513909](images/image-20230604231513909.png)
