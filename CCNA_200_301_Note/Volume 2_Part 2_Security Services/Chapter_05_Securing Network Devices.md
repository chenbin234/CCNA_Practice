# Securing Network Devices

## 1 **Securing IOS Passwords**

<img src="images/image-20230604183447100.png" alt="image-20230604183447100" style="zoom: 67%;" />

### 1.1 **Encrypting Older IOS Passwords with service password-encryption**

<img src="images/image-20230604183705631.png" alt="image-20230604183705631" style="zoom:50%;" />

<img src="images/image-20230604183738263.png" alt="image-20230604183738263" style="zoom:50%;" />

<img src="images/image-20230604184009464.png" alt="image-20230604184009464" style="zoom:50%;" />



### 1.2 **Encoding the Enable Passwords with Hashes**

Cisco solved the problem of only weak ways to store the password of the **enable password** password global command by making a more secure replacement: the **enable secret** password global command. However, both these commands exist in IOS even today. 

<img src="images/image-20230604184236936.png" alt="image-20230604184236936" style="zoom:50%;" />

<img src="images/image-20230604184423097.png" alt="image-20230604184423097" style="zoom:50%;" />

<img src="images/image-20230604184455434.png" alt="image-20230604184455434" style="zoom:50%;" />

IOS now supports two alternative algorithm types in the more recent router and switch IOS images. Both use an SHA-256 hash instead of MD5

<img src="images/image-20230604184651373.png" alt="image-20230604184651373" style="zoom:50%;" />

<img src="images/image-20230604184706384.png" alt="image-20230604184706384" style="zoom:50%;" />

<img src="images/image-20230604184716692.png" alt="image-20230604184716692" style="zoom:50%;" />

### 1.3 **Encoding the Passwords for Local Usernames**

<img src="images/image-20230604184929491.png" alt="image-20230604184929491" style="zoom:50%;" />

<img src="images/image-20230604184954067.png" alt="image-20230604184954067" style="zoom:50%;" />



### 1.4 **Controlling Password Attacks with ACLs**

When an external user connects to a router or switch using Telnet or SSH, IOS uses a vty line to represent that user connection. IOS can apply an ACL to the vty lines, filtering the addresses that can telnet or SSH into the router or switch. If filtered, the user never sees a login prompt.

<img src="images/image-20230604185301529.png" alt="image-20230604185301529" style="zoom:50%;" />

The **access-class** command refers to the matching logic in **access-list 3**. The keyword **in** refers to Telnet and SSH connections into this router—in other words, people telnetting into this router. As configured, ACL 3 checks the source IP address of packets for incoming Telnet connections.



## 2 **Firewalls and Intrusion Prevention Systems**

### 2.1 **Traditional Firewalls**

**Security Zones**

<img src="images/image-20230604193049810.png" alt="image-20230604193049810" style="zoom: 50%;" />

<img src="images/image-20230604193131412.png" alt="image-20230604193131412" style="zoom:50%;" />

demilitarized zone (DMZ)



### 2.2 **Intrusion Prevention Systems (IPS)**

The IPS first downloads a database of exploit signatures. Each signature defines different header field values found in sequences of packets used by different exploits. Then the IPS can examine packets, compare them to the known exploit signatures, and notice when packets may be part of a known exploit. Once identified, the IPS can log the event, discard packets, or even redirect the packets to another security application for further examination.

<img src="images/image-20230604193408216.png" alt="image-20230604193408216" style="zoom:50%;" />

**Cisco Next-Generation Firewalls**

The following list mentions a few of the features of an NGFW. 

<img src="images/image-20230604193538733.png" alt="image-20230604193538733" style="zoom:50%;" />

<img src="images/image-20230604193554680.png" alt="image-20230604193554680" style="zoom:50%;" />

**Cisco Next-Generation IPS**

<img src="images/image-20230604193715957.png" alt="image-20230604193715957" style="zoom:50%;" />



## **Command References**

<img src="images/image-20230604193935185.png" alt="image-20230604193935185" style="zoom:50%;" />

<img src="images/image-20230604193957568.png" alt="image-20230604193957568" style="zoom:50%;" />