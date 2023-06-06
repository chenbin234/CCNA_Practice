# Cloud Architecture

## 1. **Server Virtualization**

#### 1.1 **Cisco Server Hardware**

#### 1.2 **Server Virtualization Basics**

<img src="images/image-20230606151141178.png" alt="image-20230606151141178" style="zoom:50%;" />

<img src="images/image-20230606151210429.png" alt="image-20230606151210429" style="zoom:50%;" />

#### 1.3 **Networking with Virtual Switches on a Virtualized Host**

<img src="images/image-20230606151335212.png" alt="image-20230606151335212" style="zoom:50%;" />



#### 1.4 **The Physical Data Center Network**

<img src="images/image-20230606151449493.png" alt="image-20230606151449493" style="zoom:50%;" />



## 2. **Cloud Computing Services**

The list is derived from the definition of cloud computing as put forth by the US National Institute of Standards and Technology (NIST):

<img src="images/image-20230606151959508.png" alt="image-20230606151959508" style="zoom:50%;" />

#### 2.1 **Private Cloud (On-Premise)**

<img src="images/image-20230606152217391.png" alt="image-20230606152217391" style="zoom:50%;" />











#### 2.2 **Public Cloud**

<img src="images/image-20230606152247230.png" alt="image-20230606152247230" style="zoom:50%;" />



#### 2.3 **Cloud and the “As a Service” Model**

**Infrastructure as a Service**

<img src="images/image-20230606152339381.png" alt="image-20230606152339381" style="zoom:50%;" />

**Software as a Service**

<img src="images/image-20230606152439585.png" alt="image-20230606152439585" style="zoom:50%;" />

**(Development) Platform as a Service**

<img src="images/image-20230606152543451.png" alt="image-20230606152543451" style="zoom:50%;" />

**The key difference between PaaS and IaaS is** that PaaS includes many more software tools beyond the basic OS. Those tools are useful to a software developer during the software development process. Once the development process is complete, and the application has been rolled out in production, those tools are not needed on the servers running the appli- cation. So the development tools are particular to the work done when developing.



## 3. **WAN Traffic Paths to Reach Cloud Services**

### 3.1 **Enterprise WAN Connections to Public Cloud**

**Accessing Public Cloud Services Using the Internet**

<img src="images/image-20230606153551961.png" alt="image-20230606153551961" style="zoom:50%;" />

**Pros and Cons with Connecting to Public Cloud with Internet**

the following list summarizes some **good reasons** to use the Internet as the WAN connection to a public cloud service:

<img src="images/image-20230606153744254.png" alt="image-20230606153744254" style="zoom:50%;" />

Those **negatives** for using the Internet for public cloud access are

![image-20230606153811685](images/image-20230606153811685.png)



**Private WAN and Internet VPN Access to Public Cloud**

![image-20230606153920028](images/image-20230606153920028.png)

**Pros and Cons of Connecting to Cloud with Private WANs**



**Intercloud Exchanges**

Generically, the term intercloud exchange has come to be known as a company that creates a private network as a service. First, an intercloud exchange connects to multiple cloud pro- viders on one side. On the other side, the intercloud connects to cloud consumers. Figure 15-15 shows the idea.

<img src="images/image-20230606154421139.png" alt="image-20230606154421139" style="zoom:50%;" />



**Summarizing the Pros and Cons of Public Cloud WAN Options**

<img src="images/image-20230606154551119.png" alt="image-20230606154551119" style="zoom:50%;" />



### 3.2 **A Scenario: Branch Offices and the Public Cloud**













